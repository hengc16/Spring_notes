# 注入集合

* 注入array
* list
* map 
* set

//写相应的属性和set方法

```java
public class Student {
    private String[] courses;
    private List<String> list;
    private Map<String,String> map;
    private Set<String> set;

    public void setCourses(String[] courses) {
        this.courses = courses;
    }
    .....
}
```

配置相应的bean

```java
<bean id = "student"  class = "com.heng.spring5.collections.Student">
    //注入array类型属性
    <property name = 'courses'>
        <array>
            <value>java</value>
            <value>python</value>
        </array>
    </property>
    //注入list 类型属性
    <property name = 'list'>
        <list>
            <value>Bob</value>
            <value>Jack</value>
        </list>
    </property>
    //注入map类型属性
    <property name = 'map'>
        <map>
            <entry key = "Java" value = "java"></entry>
            <entry key = "Python" value = "python"></entry>
        </map>
    </property>
    //注入set类型属性
    <property name = 'set'>
        <set>
            <value>Bob</value>
            <value>Jack</value>
        </set>
    </property>
</bean>
```

