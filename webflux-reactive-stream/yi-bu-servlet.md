# 异步servlet

### 为什么用异步servlet

* 不阻塞tomcat的servlet线程
* 可以把耗时的操作放在独立的线程池里
* 我们的servlet可以继续接受下一个请求
* 少的线程完成大的吞吐量

### 同步servlet阻塞了什么

* tomcat容器的servlet线程
* 当我们的网络请求发到tomcat容器哦，tomcat容器会给每个请求一个线程去处理，线程里面会调用对应的servlet去处理。
* 当你使用同步servlet的时候，你的业务代码需要花多少时间，这个servlet线程就需要等多长时间。

### 异步servlet是怎么工作的

![](../.gitbook/assets/image%20%28359%29.png)

![](../.gitbook/assets/image%20%28364%29.png)

![](../.gitbook/assets/image%20%28360%29.png)

