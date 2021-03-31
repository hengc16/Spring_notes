# Advice

告诉Spring切面中的方都是何时何地运行，方法上注解

通知注解

@Before：在目标方法之前运行；前置通知

@After：在目标方法之后运行；后置通知

@AfterReturning：在目标方法正常返回之后；返回通知

@AfterThrowing：在目标方法抛出异常之后；异常通知

@Around：环绕通知 

 在注解中写切入点表达式：**execution\(访问权限符 返回值类型 方法全类名\(参数表\)\)**

### use case

![](../../.gitbook/assets/image%20%2876%29.png)

### 第一种方法

![](../../.gitbook/assets/image%20%2880%29.png)

![](../../.gitbook/assets/image%20%2870%29.png)

![](../../.gitbook/assets/image%20%2858%29.png)

![](../../.gitbook/assets/image%20%2878%29.png)

### 第二种方法

![](../../.gitbook/assets/image%20%2868%29.png)

