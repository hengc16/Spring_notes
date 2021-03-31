# @Aspect

切面（ASPECT）类：在上面例子中相当于自己定义的一个日志工具类。 

告诉Spring到底哪个是切面类，在类上注解`@Aspect`

```java
//切面类：

@Aspect
@Component
public class LogUtils {
    //执行前
    @Before("execution(public int com.xiao.MyProxy02.MyCalculator.*(int,int))")
    public static void before() {
        System.out.println("方法开始执行了");
    }
    //执行后
    @AfterReturning("execution(public int com.xiao.MyProxy02.MyCalculator.*(int,int))")
    public static void after() {
        System.out.println("方法执行完成了");
    }
    //出现异常
    @AfterThrowing("execution(public int com.xiao.MyProxy02.MyCalculator.*(int,int))")
    public static void exception() {
        System.out.println("方法出现异常了");
    }
    //方法结束
    @After("execution(public int com.xiao.MyProxy02.MyCalculator.*(int,int))")
    public  static void end() {
        System.out.println("方法最终结束了");
    }
}

```

