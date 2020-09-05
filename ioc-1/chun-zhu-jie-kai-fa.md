# 纯注解开发

### 创建配置类（取代之前的xml配置文件）

* 在配置类上面加上@Configuration注解，告诉spring这是你的配置类
* 接着加上@ComponentScan（basePackage = {"com.heng"}）配置文件

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



### 

