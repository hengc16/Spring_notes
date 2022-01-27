# 架构

![](<../.gitbook/assets/image (449).png>)

leader:    follower 是leader的副本    未来生产者或消费者 永远只找leader

partition ： 分区，增加并发行

topic： 主题

cluster：集群

![](<../.gitbook/assets/image (451).png>)

customer group： 消费者组，  同一个partition只能被消费者组里的一个消费者消费， 不能同时存在多个。a single partition will never be shared across several consumers within the same group unless a consumer goes offline.



zookeeper : 存储消费者消费位置信息

