# JDK9 Reactive stream

在jdk9里 也叫flow api

* 解决发布者和订阅者之间的沟通问题
* 可以防止发布者给订阅者过多的数据，导致订阅者只能被动接受，压力过大。
* 有个背压之后，订阅者如果压力大可以告诉发布者，让他少给数据。 如果压力小，可以让订阅者多给数据。

![](../.gitbook/assets/image%20%28357%29.png)

Processor 可以理解为中间的中转站，做过滤或数据处理。



### demo

![](../.gitbook/assets/image%20%28358%29.png)

### 写订阅者

![](../.gitbook/assets/image%20%28355%29.png)

### 加入中间者

![](../.gitbook/assets/image%20%28356%29.png)

