# 注入属性-内部bean

内部bean：在bean配置的文档里用嵌套的方法去注入属性。

1. 一对多的关系，部门和员工
   1. 一个部门有多个员工，一个员工属于一个部门
   2. 部门是一，员工是多。
2. 在实体类之间表示一对多的关系

```java
//部门类
public class Dept {
    private String deptName;
    public void setDeptName(String deptName) {
        this.deptName = deptName;
    }
}
```

```java
//员工类
//并用dept对象进行关联
public class Emp {
    private String ename;
    private String gender;
    private Dept dept;
    
    public void setEname(String ename) {this.ename = ename);
    public void setGender(String gender) {this.gender= gender);
    public void setDept(String dept) {this.dept= dept);  
}
```

```java
//bean 配置文件
//创建emp对象
<bean id = "emp" class = "com.heng.spring5.bean.Emp">
    //注入属性
    <property name = "ename" value = "Jay"></property>
    <property name = "gender" value = "male"> </property>
    //如果是外部bean, 可以用ref指向dept的bean对象
        //注意这里用到了内部bean, 也就是emp里的属性嵌套一个dept bean对象，对dept bean对象
        //注入属性
    <property name = "dept" >
        <bean id="dept" class = "com.heng.spring5.bean.Dept">
            <property name = "deptName" value = "hr"></property>
        </bean>
    </property>
</bean>
<bean></bean>

```

级联赋值\(Cascade assignment\)

```java
//bean 配置文件
//创建emp对象
<bean id = "emp" class = "com.heng.spring5.bean.Emp">
    //注入属性
    <property name = "ename" value = "Jay"></property>
    <property name = "gender" value = "male"> </property>
    //级联赋值1
    <property name = "dept" ref = "dept"></property>
    //级联赋值2  注意这里如果调用deptName这个属性，dept类里一定要有get method
    <property name = "dept.deptName" value = "tax dept"></property>    
</bean>


<bean id = "dept" class ="com.heng.spring5.bean.Dept">
    <property name = "dname" value = "tech dept"></property>
</bean>
```

