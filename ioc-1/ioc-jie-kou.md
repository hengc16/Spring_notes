# IOC接口

### BeanFactory 接口

* IOC容器基本实现，是spring内部的使用接口，不提供开发人员使用。
* 加载配置文件时候不会创建对象，只有在用的时候才去创建对象

### ApplicationContext接口

* BeanFactory 接口的子接口，提供更多更强大的功能，一般由开发人员使用。
* 在加载配置文件时就会创建对象。
  * 比较合理，把耗时间耗资源的事放在服务器启动的时候进去处理。

![](../.gitbook/assets/image%20%2816%29.png)

FileSystemXMLAplicationContext: 传文件在系统里的路径，绝对路径

ClassPathXmlApplicationContext: 传文件类路径，相对路径

