# 流程

![](../.gitbook/assets/image%20%28108%29.png)

### 流程

根据url去找handler

找到handler，调具体的controller（我们需要写的部分）

处理完请求，获得modelandview

根据modelandview去找相应页面

找到并跳转。

### 需要做的

springMVC把实线部分都做了，我们只需要去实现control层调业务层。和配置视图解析器所要返回的页面名字。

![](../.gitbook/assets/image%20%28113%29.png)

