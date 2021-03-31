# 外部bean注入属性

### 外部注入属性 

主要应对的是serverlet调用dao的这部分。

1. 创建2个类，service和dao
2. 在service里调用dao里的方法
3. 在spring配置文件中进行配置

```java
public class UserService {
    //创建UserDao属性
    private UserDao userDao;
    //创建set 方法
    public void setUserDao(UserDao userDao){
        this.userDao = userDao;
    }    
    public void add(){
        System.out.println("service add method.......")；
        userDao.update();
    }
}
```

通过xml去配置

```java
//创建service对象
<bean id = "userService" class = "com.heng.spring5.service.Userservice">
    //注入userDao对象
    // name 属性值：类里面属性名称
    // ref: 是你调用下面bean对象的id
    <property name="userDao" ref="userDao"> </property>
</bean>


//注意创建userDao时要找它的实现类而不是接口
<bean id = "userDao" class = "com.heng.spring5.dao.userDaoImp"></bean>
```



