# Spring boot

省去了xml configuration， 让developer可以更好focus在代码上。

### depend injection： 

* 为了解耦
* 如果一个labtop object 里面有ram，disk，和 screen这些class。 如果我们new这些class，就会出现耦合。事后很难替换。
* 如果把ram，disk，和screen放到spring object container里。 @Component
* 再通过@Autowired去container里拿ram，disk，和screen。 这样就不用new了。
* 如果有多个ram，可以通过@qualifier\("ram1"\) 在通过名字找。

