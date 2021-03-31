# 配置事务

### 配置spring-servlet.xml

```markup
<!-- 启用注解 -->
<mvc:annotation-driven />
<context:annotation-config />

<!-- 注解扫描包 -->
<context:component-scan base-package="com.slient.ssh.test">
    <context:include-filter type="annotation" expression="org.springframework.stereotype.Repository" />
    <context:include-filter type="annotation" expression="org.springframework.stereotype.Service" />
    <context:exclude-filter type="annotation" expression="org.springframework.stereotype.Controller" />
    <context:exclude-filter type="annotation" expression="org.springframework.web.bind.annotation.ControllerAdvice" />
</context:component-scan>

<aop:aspectj-autoproxy proxy-target-class="true"/>

<!-- 完成请求和注解POJO的映射 -->
<bean class="org.springframework.web.servlet.mvc.annotation.AnnotationMethodHandlerAdapter" />

<!-- SpringMVC上传文件时，需要配置MultipartResolver处理器 -->
<bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
    <property name="defaultEncoding" value="UTF-8" />
    <property name="maxUploadSize" value="3912608" />
    <property name="maxInMemorySize" value="39126080" />
</bean>

<bean id="contentNegotiationManager" class="org.springframework.web.accept.ContentNegotiationManagerFactoryBean">
    <property name="favorPathExtension" value="false" />
    <property name="favorParameter" value="false" />
    <property name="ignoreAcceptHeader" value="false" />
    <property name="mediaTypes">
        <value>
            atom=application/atom+xml
            html=text/html
            json=application/json
            *=*/*
        </value>
    </property>
</bean>

<!-- 视图解析器 -->
<mvc:annotation-driven content-negotiation-manager="contentNegotiationManager">
    <mvc:message-converters register-defaults="true">
        <bean class="org.springframework.http.converter.StringHttpMessageConverter">
            <constructor-arg value="UTF-8" />
        </bean>
    </mvc:message-converters>
</mvc:annotation-driven>

<!-- 定义JSP文件的位置 -->
<bean class="org.springframework.web.servlet.view.InternalResourceViewResolver">
    <property name="viewClass" value="org.springframework.web.servlet.view.JstlView" />
    <property name="prefix" value="/WEB-INF/jsp/" />
    <property name="suffix" value=".jsp" />
</bean>

<!-- 容器默认的DefaultServletHandler处理 所有静态内容与无RequestMapping处理的URL -->
<mvc:default-servlet-handler />

<import resource="spring-hibernate.xml"/>
```

### 配置spring-hibernate.xml

```markup
<!-- 配置c3p0数据源 -->
<bean id="dataSource" class="com.mchange.v2.c3p0.ComboPooledDataSource" destroy-method="close">
    <property name="driverClass" value="com.mysql.jdbc.Driver" />
    <property name="jdbcUrl" value="jdbc:mysql://localhost:3306/test?characterEncoding=UTF-8" />
    <property name="user" value="root" />
    <property name="password" value="000000" />
    <property name="minPoolSize" value="2" />
    <property name="maxPoolSize" value="15" />
    <property name="maxIdleTime" value="60" />
    <property name="acquireIncrement" value="3" />
    <property name="maxStatements" value="1000" />
    <property name="initialPoolSize" value="10" />
    <property name="idleConnectionTestPeriod" value="1000" />
    <property name="acquireRetryAttempts" value="5" />
    <property name="breakAfterAcquireFailure" value="false" />
    <property name="testConnectionOnCheckout" value="false" />
</bean>

<!-- 配置SessionFactory  注解形式 -->
<bean id="sessionFactory" class="org.springframework.orm.hibernate4.LocalSessionFactoryBean">
    <property name="dataSource" ref="dataSource" />
    <!-- 自动扫描包，不用手动配置实体类 -->
    <property name="packagesToScan">
        <list>
            <value>com.slient.ssh.test.bean</value>
        </list>
    </property>
    <property name="hibernateProperties">
        <props>
            <prop key="hibernate.dialect">org.hibernate.dialect.MySQLDialect</prop>
            <prop key="hibernate.current_session_context_class">org.springframework.orm.hibernate4.SpringSessionContext</prop>
            <prop key="hibernate.hbm2ddl.auto">none</prop>
            <prop key="hibernate.show_sql">true</prop>
            <prop key="hibernate.format_sql">true</prop> 
            <prop key="hibernate.use_sql_comments">true</prop>
            <prop key="hibernate.temp.use_jdbc_metadata_defaults">false</prop>
        </props>
    </property>
 </bean>

<bean id="hibernateTemplate" class="org.springframework.orm.hibernate4.HibernateTemplate">
    <property name="sessionFactory" ref="sessionFactory"></property>
</bean>

 <!-- 配置事务管理 -->
<bean id="transactionManager" class="org.springframework.orm.hibernate4.HibernateTransactionManager">
    <property name="sessionFactory" ref="sessionFactory" />
</bean>

<!-- 配置事务属性 -->
<tx:advice id="txAdvice" transaction-manager="transactionManager">
    <tx:attributes>
        <tx:method name="exists" read-only="true" />
        <tx:method name="save*" propagation="REQUIRED"/>
        <tx:method name="query*" read-only="true" />
        <tx:method name="delete*" propagation="REQUIRED"/>
        <tx:method name="*" propagation="REQUIRED"/>
    </tx:attributes>
</tx:advice>

<!-- 配置AOP切面 -->
<aop:config>
    <aop:pointcut id="bussinessService" expression="execution(public * com.slient.ssh.test..*.*(..))" />
    <aop:advisor pointcut-ref="bussinessService" advice-ref="txAdvice" />
</aop:config>

```

### 配置web.xml

```markup
<welcome-file-list>
    <welcome-file>index.jsp</welcome-file>
</welcome-file-list>

<listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
</listener> 

<servlet>
    <servlet-name>dispatcher</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
        <param-name>contextConfigLocation</param-name>
        <param-value>/WEB-INF/conf/spring-servlet.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
</servlet>
<servlet-mapping>
    <servlet-name>dispatcher</servlet-name>
    <url-pattern>/*</url-pattern>
</servlet-mapping>

<filter>
    <filter-name>encode</filter-name>
    <filter-class>org.springframework.web.filter.CharacterEncodingFilter</filter-class>
    <init-param>
        <param-name>encoding</param-name>
        <param-value>UTF-8</param-value>
    </init-param>
</filter>
<filter-mapping>
    <filter-name>encode</filter-name>
    <url-pattern>/*</url-pattern>
</filter-mapping>

```



