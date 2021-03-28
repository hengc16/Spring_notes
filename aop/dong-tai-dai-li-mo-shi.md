# 动态代理模式

### 动态代理

![](../.gitbook/assets/image%20%2855%29.png)

### InvocationHandler

![](../.gitbook/assets/image%20%2854%29.png)

### Proxy

![](../.gitbook/assets/image%20%2859%29.png)

### 代码

使用invocationHandler 和proxy去实现动态设置proxy

```java
package proxydemo2;

import java.lang.reflect.InvocationHandler;
import java.lang.reflect.Method;
import java.lang.reflect.Proxy;
//使用这个类去自动生产代理类
public class ProxyInvo implements InvocationHandler {

    //被代理的接口
    private Object target;

    public void setTarget(Object target) {
        this.target = target;
    }


    //生成代理
    public Object getProxy(){
        //3个参数， 第一个是classloader， 第二个是类的接口，第三个是invocationhandler
        return Proxy.newProxyInstance(this.getClass().getClassLoader(), target.getClass().getInterfaces(), this);
    }

    //处理代理实例，并返回实例
    @Override
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {
        //在这里加入log的method
        log(method.getName());
        Object result = method.invoke(target, args);
        return result;
    }
    //在这里写log
    public void log(String msg){
        System.out.println("LOG: " + msg + " method got accessed.");
    }
}

```



```java
public class Client {
    public static void main(String[] args) {
        //真是角色
        UserService userService = new UserServiceImp();
        //代理角色
        ProxyInvo pih = new ProxyInvo();
        //设置代理角色要代理的对象
        pih.setTarget(userService);
        //动态生成代理类
        UserService proxy = (UserService) pih.getProxy();
        //使用代理类来操作
        proxy.query();
    }
}

```

