# 使用注解实现自动装配

### 配置注解：

```markup
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xmlns:context="http://www.springframework.org/schema/context"
    xsi:schemaLocation="http://www.springframework.org/schema/beans
        https://www.springframework.org/schema/beans/spring-beans.xsd
        http://www.springframework.org/schema/context
        https://www.springframework.org/schema/context/spring-context.xsd">

    <context:annotation-config/>
</beans>
```

### 注解说明

* @Autowired: 自动装配 通过 byType， 再byName
  * 如果Autowired不能唯一自动装配上属性，则需要通过@Qualifier（value = “xxx”）
* @Nullable 字段标记了这个注解，说明这个字段可以为null
* @Resource ：自动装配 byName, 在byType

