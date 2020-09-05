# bean的生命周期

![](.gitbook/assets/image%20%2819%29.png)

class文件

```java
public class Orders{
//无参构造
    public Orders(){
        System.out.println("第一步，执行无参构造函数，创建bean实例");
    }
    private String oname;
    public void setOname(String oname) {
        this.oname = oname;
        System.out.println("第二步，调用set方法设置属性");
    }
    //创建初始化方法
    public void init(){
        System.out.println("第三部，执行初始化方法");
    }
    //创建销毁方法
    public void destroy(){
        System.out.println("第五步，手动销毁");
    }
}
```

配置文件

```java
<bean id = "orders" class = "com.heng.spring5.bean.Orders" init-method = "init">
    <property name = 'oname' value = 'phone'> </property>
</bean>
```

测试文件

```java
@Test
public void testBean(){
    ClassPathXmlApplication context = new ClassPathXmlApplicationContext("bean.xml");
    Orders orders = context.getBean("orders", Orders.class);
    System.out.println("第四步，获取创建bean实例对象");
    
    //手动让bean实例销毁
     context.close();
}
```

