# interview question

what is aop?



what is advice?



what is joint point

*  Join point is a point of execution of the program, such as the execution of a method or the handling of an exception. In Spring AOP, a **join point always represents a method execution**. For example, all the methods defined inside your `EmployeeManager` interface cab be considered joint points if you apply any cross-cutting concern of them.

what is pointcut

*  **Pointcut is a predicate or expression that matches join points.** Advice is associated with a pointcut expression and runs at any join point matched by the pointcut \(for example, expression “`execution(* EmployeeManager.getEmployeeById(..))`” to match `getEmployeeById()` the method in `EmployeeManager` interface\). The concept of join points as matched by pointcut expressions is central to AOP, and Spring uses the AspectJ pointcut expression language by default.

how you handle transactions

what is the difference between jar file and war file

war contains web-inf and meta-inf directories,  jar with any desired structure.

JAR files allow us to package multiple files in order to use it as a library, plugin, or any kind of application. On the other hand, WAR files are used only for web applications.

[https://www.baeldung.com/java-jar-war-packaging](https://www.baeldung.com/java-jar-war-packaging)

