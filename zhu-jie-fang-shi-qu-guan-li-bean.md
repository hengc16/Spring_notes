# 注解方式去创建bean对象

### 什么是注解？

* 注解是代码特殊标记，格式： @注解名称（属性名称=属性值，属性名称=属性值。。。）
* 注解目的：简化xml配置

### spring针对bean管理提供的注解：

* @Component: 
* @Service :业务逻辑层
* @Controller: web层
* @Repository : DAO层
* 上面4个注解都可以用来创建bean实例

### 基于注解方式创建bean对象：

1. 引入依赖
   1. spring-aop
2. 开启组件扫描
   1. 如果扫描多个包，每个包路径用, 隔开
   2. 或者直接扫描多个包的LCA
   3. `<context:componenet-scan base-package ="com.heng"> </context:component-scan>`
3. 在class里标记注解，用注解方式创建对象，如果value不写，默认为你class名称（但是首字母小写）

![](.gitbook/assets/image%20%2823%29.png)

### 配置开启组件扫描：

* 自己重写过滤器
* 只扫描xxx

![](.gitbook/assets/image%20%2827%29.png)

-除了xxx，都扫描

![](.gitbook/assets/image%20%2829%29.png)



