# token

![](../.gitbook/assets/image%20%28274%29.png)

* 用户认证成功，服务端生成一个token发给用户端
  * 用户端把token存在cookie或localstorage里
* 用户每次请求服务端，带上token
  * 服务端收到token，就可以验证并确认用户身份。

不同：

session需要存在服务端。如果当前服务端down了，用户需要再次认证。

