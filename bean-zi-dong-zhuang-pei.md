# bean自动装配

使用bean tag里的autowire属性类自动装配

atuowire 可以装配byName 或者byType

![](.gitbook/assets/image%20%2824%29.png)

如果定义多个相同类型的bean，之后autowire byType，spring会报错，因为类型相同，spring不知道去哪个bean

### 基于XML的自动装配很少用到，基本都是注解装配。

