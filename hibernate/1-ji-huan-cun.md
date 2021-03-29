# 1级缓存

![](../.gitbook/assets/image%20%2896%29.png)

2个get， 但只向数据库发了一条sql 语句

### flush

* 使seesion缓存中对象的状态保持一致， 为了保持一致，则可能会发送对应的sql语句。如果状态一样，则不需要向数据库发送sql语句。
* 在transaction的commit\(\)方法中：先调用session的flush，再提交事务。
* flush 可能会发送sql语句，但不会提交事务。，
* 注意： 在未提交事务或调用session.flush\(\)之前，也有可能进行flush\(\)操作
  * 执行HQL 或QBC查询，会先进行flush（）操作，来保证得到最新的记录。

![](../.gitbook/assets/image%20%2894%29.png)

![](../.gitbook/assets/image%20%2890%29.png)

![](../.gitbook/assets/image%20%2891%29.png)

![](../.gitbook/assets/image%20%2889%29.png)

