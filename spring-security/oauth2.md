# Oauth2

![](../.gitbook/assets/image%20%28302%29.png)

Oatuh2.0的服务提供方涵盖2个服务。授权服务\(authorization server，也就是认证服务） 和资源服务\(resource server\).

Authorization Server要对用户进行验证并颁发token，对应request要有spring mvc controll来进行实现，以下endpoint必须要实现

* AuthorizationEndpoint 服务于认证请求，默认url是/oauth/authorize
* TokenEndpoint 服务于访问token请求，默认url是/oauth/token

资源服务\(resource server\) 要包含对资源的保护，对非法请求的拦截， 对request里的token进行分析鉴权。

* OAuth2AuthenticationProcessingFilter 用来对请求的身份鉴权



