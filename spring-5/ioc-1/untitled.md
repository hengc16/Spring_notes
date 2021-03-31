# @方式实现注入

![](../../.gitbook/assets/image%20%2830%29.png)

### AutoWired

1. 把service和dao对象创建，在service和dao类添加创建对象注解
2. 在属性上面添加注解

![](../../.gitbook/assets/image%20%2836%29.png)

### Qualifier

* 需要和@autowired一起使用
* autowired根据类型注入，如果类型是多态，有多种实现类，可以通过qualifier去根据名字找指定实现类。

![](../../.gitbook/assets/image%20%2835%29.png)

### Resource

![](../../.gitbook/assets/image%20%2826%29.png)

* 注意Resource是javax包了的，不是spring包的。Spring更推荐使用autowired和qualifier

### Value

* 主要是针对于普通数据类型，如果string，int等
* 开发中会用到@value去动态读取服务器端口号，或者配置环境等，或将配置文件中的值注入到相应class里。

