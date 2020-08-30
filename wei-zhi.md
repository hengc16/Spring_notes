# 位置

* 用于开发微服（microservices）

![](.gitbook/assets/image%20%285%29.png)

* 以上每一个服务，如会员服务，商品服务都是一个单独的开发，测试，部署
* 因为拆分成了微服务，耦合度变低了。
* 注意单靠spring——boot是无法完成部署的

![](.gitbook/assets/image%20%289%29.png)

* 关于管理部署是依赖于spring\_cloud。 解决Load-balancing, circuit-breaking,distributed tracing, and monitoring.
* 专注于开发微服务还是用spring\_boot



