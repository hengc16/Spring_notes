# 引入外部文件

这里使用的是druid连接池去连接数据库

直接引入

```java
<bean id = "dataSource" class = "com.alibaba.druid.poll.DruidDataSource">
    <property name = "driverClassName" value = "com.mysql.jdbc.Driver"></property>
    <property name = "url" value = "jdbc:mysql://localhost:3306/userDb"></property>
    <property name = "username" value = "root" > </property>
    <property name = "password" value = "root"> </property>
</bean>
//你会发现这里面都是的数据都是写好的 
```

通过外部属性文件来配置连接池

1. 先创建一个properties的文件，写数据库的信息

![](.gitbook/assets/image%20%2822%29.png)

2. 读取properites的内容，需要通过spring-context去做引用

* 先加入配置信息

![](.gitbook/assets/image%20%2828%29.png)

* 在spring配置文件中，使用context tag去引入外部文件

![](.gitbook/assets/image%20%2830%29.png)

修改property里的

![](.gitbook/assets/image%20%2824%29.png)

