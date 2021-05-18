# 认证流程

![](../.gitbook/assets/image%20%28282%29.png)

* 用户提交密码
* 由usernamepasswordauthenticationfileter 来处理请求
  * 委托给authentication manager去做
    * 又交给DAOauthenticationprovider去做
      * 通过loadUserByUsername 来找用户是否存在
        * 如果存在，验证密码
        * 如果不存在，返回
* 通过securityConextHolder 将authentication保持到安全上下文。
* 通过改userdetailservice来实现验证
  * 将来在数据库拿用户信息



### passwordEncoder

![](../.gitbook/assets/image%20%28284%29.png)



