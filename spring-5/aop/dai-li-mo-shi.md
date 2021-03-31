# 代理模式

SpringAOP的底层

### 静态代理：

```java
public class Client {
    public static void main(String[] args) {
        UserService userService = new UserServiceImp();
        UserServiceProxy userServiceProxy = new UserServiceProxy(userService);
        userServiceProxy.add();
    }
}

public interface UserService {
    public void add();
    public void delete();
    public void update();
    public void query();
}
//基本的crud method
public class UserServiceImp implements UserService{
    @Override
    public void add() {
        System.out.println("added");
    }

    @Override
    public void delete() {
        System.out.println("deleted");
    }

    @Override
    public void update() {
        System.out.println("updated");
    }

    @Override
    public void query() {
        System.out.println("Found");
    }
}
//通过代理来加feature
public class UserServiceProxy implements UserService {
    private UserService userService;

    public UserServiceProxy(UserService userService) {
        this.userService = userService;
    }

    @Override
    public void add() {
        log("add");
        System.out.println( "added");
    }

    @Override
    public void delete() {
        log("delete");
        System.out.println("deleted");
    }

    @Override
    public void update() {
        log("update");
        System.out.println("updated");
    }

    @Override
    public void query() {
        log("query");
        System.out.println("Found");
    }
    public void log(String method){
        System.out.println("log " + method + " is called");
    }
}
```

### 优缺点

![](../../.gitbook/assets/image%20%2853%29.png)

