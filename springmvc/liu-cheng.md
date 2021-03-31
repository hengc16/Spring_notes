# 流程

![](../.gitbook/assets/image%20%28109%29.png)

### 流程

根据url去找handler

找到handler，调具体的controller（我们需要写的部分）

处理完请求，获得modelandview

根据modelandview去找相应页面

找到并跳转。

### 需要做的

springMVC把实线部分都做了，我们只需要去实现control层调业务层。和配置视图解析器所要返回的页面名字。

![](../.gitbook/assets/image%20%28116%29.png)

### 一次请求

```text
MVC一次请求的全过程
1.用户发起请求
2.中央控制器dispatcherServlet
3.dispatcherServlet调用处理器映射器handlerMapping
4.handlerMapping找到对应处理器，并返回对应的处理器对象handler给中央控制器
5.dispatcherServlet将handler给handlerAdapter处理器适配器
6.handlerAdapter调用handler处理器（controller）
7.controller调用业务层
8.业务层调用dao层
9.dao层调用jdbc或Mybatis对数据库操作返回给业务层
10.controller得到业务层返回的数据，返回modelandview
11.dispatcherServlet调用视图解析器ViewResolve解析modelandview
12.ViewResolve返回view
13.dispatcherServlet将view给jsp进行渲染呈现给用户
```

