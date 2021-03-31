# 自动配置

### pom.xml

![](../.gitbook/assets/image%20%28145%29.png)

### 启动器（starters\)

![](../.gitbook/assets/image%20%28136%29.png)

### 主程序

![](../.gitbook/assets/image%20%28140%29.png)

![](../.gitbook/assets/image%20%28142%29.png)

1. springboot在启动的时候，从类路径/META-INF/spring.factories获取指定的值。
2. 在这些自动配置的类导入容器，自动配置就会生效，并帮我们进行自动配置。
3. 以前我么需要自动配置的东西，现在springboot帮我们做了。
4. 整合JavaEE, 解决方案和自动配置的东西都在spring-boot-autoconfigure-2.2.0RELEASE.jar包下
5. 它会把所有需要导入的组件，以类名的方式返回，这些组件就会被添加到容器里。
6. 容器中也会存在很多xxxAutoConfiguration的文件，这是这些类给容器中导入这个场景需要的所有组件，并自动配置。@Configuration
7. 有了自动配置类，免去了我们配置的工作。



