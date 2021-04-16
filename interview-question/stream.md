# stream

```text
stream

map 

filter 

```

```text
hashmap  currentmap


```

```text
microservices
```

```text
lazy loading eager loading
```

```text
predefined funtional interface
```

```text
mongodb vs dynamodb
```

```text
exceptionhandler

```

#### Q24. What Does the _@ExceptionHandler_ Annotation Do?

**The** _**@ExceptionHandler**_ **annotation allows us to define a method that will handle the exceptions**. **We may use the annotation independently, but it's a far better option to use it together with the** _**@ControllerAdvice**_**.** Thus, we can set up a global error handling mechanism. **In this way, we don't need to write the code for the exception handling within every controller**.

Let's take a look at the example from our article about [Error Handling for REST with Spring](https://www.baeldung.com/exception-handling-for-rest-with-spring):

```text
@ControllerAdvice
public class RestResponseEntityExceptionHandler
  extends ResponseEntityExceptionHandler {

    @ExceptionHandler(value = { IllegalArgumentException.class,
      IllegalStateException.class })
    protected ResponseEntity<Object> handleConflict(RuntimeException ex,
      WebRequest request) {
        String bodyOfResponse = "This should be application specific";
        return handleExceptionInternal(ex, bodyOfResponse, new HttpHeaders(),
          HttpStatus.CONFLICT, request);
    }
}
```

We should also note that this will provide _@ExceptionHandler_ methods to all controllers that throw _IllegalArgumentException_ or _IllegalStateException_. The exceptions declared with _@ExceptionHandler_ should match the exception used as the argument of the method. Otherwise, the exception resolving mechanism will fail at runtime.

**One thing to keep in mind here is that it's possible to define more than one** _**@ExceptionHandler**_ **for the same exception. We can't do it in the same class though since Spring would complain by throwing an exception and failing on startup.**

On the other hand, **if we define those in two separate classes, the application will start, but it'll use the first handler it finds, possibly the wrong one**.

```text
autowire
```

```text
IOC
```

```text
AOP
```

```text
completable future
```

```text
yeild join
```

```text
cap   mongodb support which two
```

```text
cluster index vs non index
```

```text
cascade 

```

It is used in conjunction with ON DELETE or ON UPDATE. It means that the child data is set to NULL when the parent data is deleted or updated.

```text
controlleradvice
```

