# bean管理

1. bean管理分为：
   1. spring创建对象
   2. spring注入属性
2. bean管理操作：
   1. 基于xml方式实现
   2. 基于注解方式实现

基于XML方式实现bean管理：

```markup
//配置User对象创建
<bean id = 'user' class = "com.heng.spring5.User"> </bean>
```

1. 在spring配置文件里使用bean标签，标签里添加对应的属性，就可以实现对象创建了。
2. 在bean标签里有很多属性
   1. id属性： 就是对象的唯一标识，用于查找
   2. class 属性： 类全路径，包的path
   3. name属性：是id的前辈，被id顶替了，name可以接受特殊符号。

基于XML注入属性：

1. DI:依赖注入，就是注入属性
   1. 传统set方法，改属性值
   2. 使用有参construct去注入。

```java
public class Book {
    private string name;
    private string author;
    public void setName (String name) {
        this.name = name;
    } 
    public void setAuthor(String author) {
        this.author = author;
    }
}
```

2. 在spring配置文件中通过bean标签创建对象，和配置属性注入

```java
<bean id = 'book' class = "com.heng.spring5.Book"> 
    <property name = 'name' value = 'a' > </property>
    <property name = 'author' value = 'b'> </property>
</bean>
```

