# bean的作用域

### 作用域

bean可以为singleton，或者是多实例对象

默认情况下为单实例对象。

![](../.gitbook/assets/image%20%2818%29.png)

如何设置singleton。

可以通过bean tag里的scope 属性来操作

scope属性 可以通过设置singleton来表示单实例

prototype来表示多实例。

![](../.gitbook/assets/image%20%2817%29.png)

### singleton vs prototype

* 设置scope值为singleton时候，加载 spring配置文件时候就会创建单实例对象
* 设置为prototype的时候，不是在加载spring配置文件时创建对象，卫视在调用getBean方法的时候创建多实例对象

