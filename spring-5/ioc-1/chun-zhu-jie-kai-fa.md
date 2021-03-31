# 基于java的配置bean依赖

### 创建配置类（取代之前的xml配置文件）

* 在配置类上面加上@Configuration注解，告诉spring这是你的配置类
* 接着加上@ComponentScan（basePackage = {"com.heng"}）配置文件

![](../../.gitbook/assets/image%20%2856%29.png)

### 测试类

```java
@Test
public void testService2(){
    //加载配置文件
    ApplicationContext context =
     new AnnotationConfigApplicationContext(SpringConfig.class);
     UserService userService = context.getBean("userService", UserService.class);
     sout(userService);
     userService.add();
}
```



### [https://www.bilibili.com/video/BV1WE411d7Dv?p=16](https://www.bilibili.com/video/BV1WE411d7Dv?p=16)

