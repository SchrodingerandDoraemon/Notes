### data validation
Spring MVC does the task of data validation using the validator object which implements the Validator interface. In the custom validator class that we have created, we can use the utility methods of the ValidationUtils class like rejectIfEmptyOrWhitespace() or rejectIfEmpty() to perform validation of the form fields.
```
@Component
public class UserValidator implements Validator
{
   public boolean supports(Class clazz) {
       return UserVO.class.isAssignableFrom(clazz);
   }
 
   public void validate(Object target, Errors errors)
   {
       ValidationUtils.rejectIfEmptyOrWhitespace(errors, "name", "error.name", "Name is required.");
       ValidationUtils.rejectIfEmptyOrWhitespace(errors, "age", "error.age", "Age is required.");
       ValidationUtils.rejectIfEmptyOrWhitespace(errors, "phone", "error.phone", "Phone is required.");
   }
}
```

In the fields that are subject to validation, in case of errors, the validator methods would create field error and bind that to the field.

To activate the custom validator as spring bean, then: We have to add the @Component annotation on the custom validator class and initiate the component scanning of the package containing the validator declarations by adding the below change:

```
<context:component-scan base-package="com.interviewbit.validators"/>
```

OR

The validator class can be registered in the context file directly as a bean as shown:
```
<bean id="userValidator" class="com.interviewbit.validators.UserValidator" />
```

### how do you do the pagination /

2.	how do you solve the pagination problem!



### bean scope
Note that there are five supported scopes:
- Singleton. ()
- Prototype
- Request
- Session
- Global-session

Are Singleton Beans Thread-Safe?

No, singleton beans are not thread-safe, as thread safety is about execution, whereas the singleton is a design pattern focusing on creation. Thread safety depends only on the bean implementation itself.

### @Qualifier
The @Qualifier annotation is used to resolve the autowiring conflict, when there are multiple beans of same type. T
