# controller

使用@controller

1. @Controller：告诉Spirng这是一个控制器，交给IOC容器管理
2. @RequestMapping\("/hello01"\)：/ 表示项目地址，当请求项目中的hello01时，返回一个/WEB-INF/page/success.jsp页面给前端

```java
@Controller
public class HelloController {

    @RequestMapping("/hello01")
    public String toSuccess(){
        System.out.println("请求成功页面");
        return "success";
    }
    @RequestMapping("/hello02")
    public String toError() {
        System.out.println("请求错误页面");
        return "error";
    }
}
```

这里返回的“success” 是个视图解析器 拿去做拼接的。会去配置路径里找success.jsp



