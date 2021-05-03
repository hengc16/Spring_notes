# caching

### first level caching 

by default, hibernate same session fetch the same query, it will use first level caching. 

![](../.gitbook/assets/image%20%28270%29.png)

只会去database fetch一次

### second level caching 

for multi-session to share data for caching.

* need to use third party library  like ehcache 
* add library to pom.xml
* add ehcache to hibernate configuration file
* add @cachable @cache to Entity 

configuration：

![](../.gitbook/assets/image%20%28268%29.png)

add annotation

![](../.gitbook/assets/image%20%28265%29.png)

by default, 2nd level caching does not support sql query,  need to invoke it to support.

![](../.gitbook/assets/image%20%28272%29.png)

![](../.gitbook/assets/image%20%28269%29.png)

let the query to use cache. 



