# 会话（session）

基于session的认证

![](../.gitbook/assets/image%20%28275%29.png)

* 用户登陆成功
* 服务端创建一个session
  * session存储用户的信息
* 服务端返回一个seesion id 给用户
  * 客户端把session id 存在了cookie里
* 用户再次访问web服务，带着session id。
  * web服务端会验证用户的session id是否存在
  * 如果存在，就不要求用户再次认证了。

