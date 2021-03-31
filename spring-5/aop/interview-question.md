# interview question

what is aop?



what is advice?



what is joint point

*  Join point is a point of execution of the program, such as the execution of a method or the handling of an exception. In Spring AOP, a **join point always represents a method execution**. For example, all the methods defined inside your `EmployeeManager` interface cab be considered joint points if you apply any cross-cutting concern of them.

what is pointcut

*  **Pointcut is a predicate or expression that matches join points.** Advice is associated with a pointcut expression and runs at any join point matched by the pointcut \(for example, expression “`execution(* EmployeeManager.getEmployeeById(..))`” to match `getEmployeeById()` the method in `EmployeeManager` interface\). The concept of join points as matched by pointcut expressions is central to AOP, and Spring uses the AspectJ pointcut expression language by default.

how you handle transactions

what is the difference between jar file and war file

