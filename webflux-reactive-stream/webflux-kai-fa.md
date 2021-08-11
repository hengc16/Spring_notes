# webflux开发

### Reactor

* jdk8 stream + jdk9 reactive stream
* mono 0 - 1 个元素
* Flux 0 - n 个元素

![](../.gitbook/assets/image%20%28357%29.png)

### RestController 新老对比

![](../.gitbook/assets/image%20%28372%29.png)

![](../.gitbook/assets/image%20%28361%29.png)

老的占用了5秒钟

新的Mono 不到一秒

### Flux

![](../.gitbook/assets/image%20%28365%29.png)

![](../.gitbook/assets/image%20%28371%29.png)

每一秒出一个数据

