# JWT（json web token）

并不是去database check用户密码是否正确， 而是用来保证用户是原来的用户，并免去2次登陆。

![](../.gitbook/assets/image%20%28180%29.png)

原本用户的信息是存在session里放在server memory上， JWT可以把用户信息安全的存在一个json token里。

![](../.gitbook/assets/image%20%28172%29.png)

multi-server

![](../.gitbook/assets/image%20%28178%29.png)

* 如果用户将session存在bank server上，他需要输入密码才能登陆retirement
* 如果用JWT, 只要bank和retirement的secret key 一样，用户就可以免登陆。

