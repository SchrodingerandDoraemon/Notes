Java Core

1.	advantage of Java
2.	Java is one of the fastest and most energy-efficient object-oriented language, Java is platform-independent.

1.	java is dynamic or static
Java is statically-typed, so it expects its variables to be declared before they can be assigned values. 


Functional interface (means it represent functionality)
A functional interface is an interface with one single abstract method. It can be used as Lambda expression instead.
It is not madatory but recommended to use @FunctionalInterface annotation to avoid the addition of extra methods accidentally.
consumer: consume a value and return a void
Supplier: supply a value
Function: map a value to different value
predicate: test a condition


interface vs abstract class
Interface vs Abstract class (multi-inheritance+ final+ access modifier)
1.	Interface can do multi-inheritance.
2.	Final Variables: Variables declared in interface are by default final. An abstract class may contain non-final variables.
3.	Accessibility of Data Members: Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.


The final keyword can be used with class method and variable. A final class cannot be inherited, a final method cannot be overridden and a final variable cannot be reassigned.

The finally,used in try-catch, whatever exception happened or not, the finally block will excuted. Using a finally block allows you to run any cleanup-type statements.

finalize() method of Object class is a method that the Garbage Collectoralways calls just before the destroying the object which is eligible for Garbage Collection, so as to perform clean-up activity. Clean-up activity means closing the resources associated with that object like Database Connection, Network Connection or we can say resource de-allocation. Remember it is not a reserved keyword. Once the finalize method completes immediately Garbage Collector destroy that object.

Why finalize method is used()?
finalize() method releases system resources before the garbage collector runs for a specific object. JVM allows finalize() to be invoked only once per object.


Optional has a special Optional.empty() value instead of wrapped null. Thus it can be used instead of a nullable value to get rid of NullPointerException in many cases.![image](https://user-images.githubusercontent.com/35554521/151460515-40324455-ce0c-4eb8-aef8-f880ba32abef.png)

A functional interface is an interface with one single abstract method. It can be used as Lambda expression instead.

how does hashmap work
blabla, hashmap is not thread-safe. Hashtable is thread-safe




# database
### why no sql:
sql is not scalable

6.	did you use Hibernate with RDB![image](https://user-images.githubusercontent.com/35554521/151684929-58dd8e81-b3a2-41f6-82d4-f7bd50e61894.png)



### JPA pros:
JPA data is represented by classes and objects rather than by tables and records as in JDBC. Using plain old Java objects (POJO) to represent persistent data can significantly simplify database programming
1. Developer Productivity, no sql query, data is represented by object. It also provides a simple but very efficient API to implement basic CRUD operations. 
2. Database Independent. each database uses a slightly different dialect. This becomes a huge issue if your statements have to run on different databases.
3. Avoid Unnecessary Queries
4. Caching




# Spring ![image](https://user-images.githubusercontent.com/35554521/151683112-d7a8d446-8f28-497e-a951-986c6a76a32a.png)
![image](https://user-images.githubusercontent.com/35554521/151683113-55e7af99-b1a6-42ab-9932-46a125ac93b4.png)
![image](https://user-images.githubusercontent.com/35554521/151683115-3682976a-d4df-43d5-9c0e-9a1e78e0c54c.png)


## REST
#### why rest api
1. REST is much easier than other approaches such as SOAP which keeps developers from having to reinvent the wheel as far as HTTP request operations go.
2. Scalability. This is one of the best features that makes REST stands out when compared to others. Separation of client and server in REST architecture allows the developers to scale apps more easily. Let’s look at the two more reasons that make your app scalable if it uses REST API. stateless and  JSON(Faster Data Interchange Format)
3. Cacheable. cache save the data for the future so that it can be returned faster when the client makes the same request in the future. Caching reduce the load on the server that helps in decreasing the average response time. 
4.  easily transfer the data from one server to another server.It also allows you to hosts the back and front end on different servers. 



### cons of rest
One of the disadvantages of RESTful APIs is that you can lose the ability to maintain state in REST, such as within sessions. It can also be more difficult for newer developers to use.


400 vs 500
A 4xx code indicates an error caused by the user, whereas 5xx codes tell the client that they did everything correctly and it’s the server itself who caused the problem.

10.	How do you test your restful API!



Hibernate

Cascade delete
 A deletion that triggers another deletion in the related entity.


IOC
The approach of outsourcing the creation and management of objects to the spring.  Normally, when we need a new object, we have to create new one. But in spring, there is concept called container, which will create the object for us, so we can directly use them. Factory design pattern. Loosely coupled, It manages an object's life-cycle and configuration. 

AOP
It does so by adding additional function (an advice) to existing code without modifying the original code. And the new feature we just added can be used in other place as well, so it also reduced the duplicated code.
Loosely coupled. 
The most common use cases that I’ve come into are things like transaction management, logging, caching and of course, security is a great place to use Aspects.

2.	bean scope in spring
Singleton. Prototype, Request, Session, Global-session


what is singleton
a class/bean to one "single" instance.

can we put singleton inside prototype
yes, but not the other way.

Hibernate v.s. Spring Data JPA
Java Persistence API (JPA)
Hibernate is a JPA provider and ORM. Spring Data JPA is an abstraction that makes working with the JPA provider less verbose. Using Spring Data JPA you can eliminate a lot of the boilerplate code involved in managing a JPA provider like Hibernate. Normally, we use them together



#### how to write SOAP api in spring!
1. maven pom.xml add parent and dependency
2. create the domain (methods and parameters) for our service first, use an XML schema file (XSD) that Spring-WS will export automatically as a WSDL
3. generate the Java classes from the XSD
4. Add the SOAP Web Service Endpoint
5. create a class for configuring the Spring message dispatcher servlet to receive the request
6. test

#### Spring boot advantage / why spring boot
- Easy development, setup and management
- No war files deployment
- Standalone applications
- Tomcat, Jetty, or Undertow embedding
- No XML configuration
- Less source code
- Out-of-the-box functionality
- Community


# circuit breaker
The circuit breaker is fault-tolerance technique that monitors and detects when a service is behaving abnormally. It temporarily rejects those calls until the service becomes healthy again. Netflix Hystrix is an open source library which provides this solution. 

How do you include Hystrix in your project?
 FAQKey Concept
To include Hystrix in your project, use spring-cloud-starter-netflix-hystrix dependency and @EnableCircuitBreaker annotation on the Spring Boot Application class.

Use the @HystrixCommand annotation on the method for which fallback method has to be applied.


### diff spring singleton vs java singleton!
The Java singleton is scoped by the Java class loader, the Spring singleton is scoped by the container context.

Which basically means that, in Java, you can be sure a singleton is a truly a singleton only within the context of the class loader which loaded it. Other class loaders should be capable of creating another instance of it (provided the class loaders are not in the same class loader hierarchy), despite of all your efforts in code to try to prevent it.

In Spring, if you could load your singleton class in two different contexts and then again we can break the singleton concept.

So, in summary, Java considers something a singleton if it cannot create more than one instance of that class within a given class loader, whereas Spring would consider something a singleton if it cannot create more than one instance of a class within a given container/context.



## microservice
#### why microservice/ pros of microservice
- Independent Development:	All microservices can be developed independently based on their individual functionality
- Independent Deployment:	Based on their services, they can be individually deployed in any application
- Fault Isolation:	Even if one service of the application does not work, the system still continues to function
- Mixed Technology Stack:	Different languages and technologies can be used to build different services of the same application
- Granular Scaling	Individual components can scale as per need, there is no need to scale all components together

### cons of microservice
1. Increases delay due to remote calls
2. Increased efforts for configuration and other operations
3. Difficult to maintain transaction safety
4. Difficult to code between services

#### how do you deploy your microservice!

what is DAO layer
DAO is Data Access Object which is used within Persistence Layer to make Database Transaction. For example , the class holding the Database connection and CRUD methods.
The persistence layer of enterprise applications serves as an intermediary between the business functions of the application and the data it stores in a relational database. This function of the persistence layer is also known as object-relational mapping because it maps Java objects to relational data.




explain MVC based on your project feature! /MVC
7.	how does springmvc work!

spring bean lifecycle


any problems you met with bean

what is prototype
Prototype: A new instance will be created for a single bean definition every time a request is made for that bean

3.	Was your web application in microservice architecture in Spring Boot tech stacks!
Spring security

6.	What dependency packages have you used in previous projects?!

7.	What are the annotations you used for the restful API in the Spring Boot framework?

8.	What is @PathVariable?

### @RestController v.s. @Controller
in order to simplify the creation of RESTful web services. It's a convenient annotation that combines @Controller and @ResponseBody, which eliminates the need to annotate every request handling method of the controller class with the @ResponseBody annotation.
 
@ResponseBody. This annotation enables automatic serialization of the return object into the HttpResponse.


### annotation config vs xml config
annotation is more concise. Using "component-scan" to autoload classes.

XML excels at wiring up components without touching their source code or recompiling them. The key difference is that you don't have to recompile the code for all changing server-specific configurations, just edit the xml file.

### Static content vs Dynamic content
Static content is any file that is stored in a server and is the same every time it is delivered to users. HTML files and images are examples of this kind of content. Static content is like a newspaper: once an issue of a newspaper is published, it features the same articles and photos all day for everyone who picks up a copy, no matter what new developments transpire during the day.

Dynamic content is content that changes based on factors specific to the user such as time of visit, location, and device. A dynamic webpage will not look the same for everybody, and it can change as users interact with it – like if a newspaper could rewrite itself as someone is reading it. This makes webpages more personalized and more interactive.

### application server v.s. web server
<img width="1419" alt="Screen Shot 2022-01-30 at 4 19 55 PM" src="https://user-images.githubusercontent.com/35554521/151718387-2128a2fa-4314-4279-bddb-72cc8c51a806.png">


3.	Spring Boot experience!



20.	spring security experience!

21.	how to do security(authentication or authorization)

15.	Spring Batch Experience ![image](https://user-images.githubusercontent.com/35554521/151684868-d2d45faf-ae44-4186-a12a-0f44d0f15c04.png)

19.	How will you implement a singleton object in java?


5.	What tool did you use to deploy your web application? 

when will spring boot inject prototype bean!

14.	How do your microservice modules do authentication/authorization

6.	how to execute spring boot spring!

2.	design microservice - what will you consider?

5.	Have you worked with multi thread architecture you have used in microservice architecture?

How to keep requests in order during multithreading scenario in the web application? 


7.	how to do authenticate
8.	how to do authorization
9.	microservice components

7.	microservice architecture!

3.	monolithic vs microservice!

### BeanFactory v.s. ApplicationContext
BeanFactory is the most basic version of IOC containers, and the ApplicationContext extends the features of BeanFactory.
- BeanFactory loads beans on-demand(lazy loading), while ApplicationContext loads all beans at startup(eager loading)
- ApplicationContext is more suitable for enterprise applications. For instance, it provides messaging (i18n or internationalization) functionality, event publication functionality, annotation-based dependency injection, and easy integration with Spring AOP features.
- The ApplicationContext automatically registers BeanFactoryPostProcessor and BeanPostProcessor at startup. On the other hand, the BeanFactory does not register these interfaces automatically.
- Therefore, it's generally recommended to use the ApplicationContext, and we should use BeanFactory only when memory consumption is critical.


#### when to use eager loading
1. Use Eager Loading when the relations are not too much. Thus, Eager Loading is a good practice to reduce further queries on the Server.
2. Use Eager Loading when you are sure that you will be using related entities with the main entity everywhere.
3. when there is a high ping between your web and sql servers

#### When to use lazy loading
1. Use Lazy Loading when you are using one-to-many collections.
2. Use Lazy Loading when you are sure that you are not using related entities instantly.

### What is a bean in Spring?
A bean is an object that is instantiated, assembled, and otherwise managed by a Spring IoC container.

#### How to access beans in spring?
applicationContext.getBean("beanname")

### What is dependency injection?
Dependency injection means giving an object its instance variables. 
Dependency injection is basically providing the objects that an object needs (its dependencies) instead of having it construct them itself.

Dependencies can be injected into objects by many means (such as constructor injection or setter injection). One can even use specialized dependency injection frameworks (e.g. Spring) to do that.

### Which way is the best way to do bean injection?
A class that takes a required dependency as a constructor argument can only be instantiated if that argument is provided (you should have a guard clause to make sure the argument is not null) (or use a non-nullable type in Kotlin). A constructor therefore enforces the dependency requirement whether or not you're using Spring, making it container-agnostic.

If you use setter injection, the setter may or may not be called, so the instance may never be provided with its dependency. The only way to force the setter to be called is using @Required or @Autowired , which is specific to Spring and is therefore not container-agnostic.

So to keep your code independent of Spring, use constructor arguments for injection. This applies to tests; you'll have an easier time instantiating and testing the class in a normal unit test, without needing to configure an application context or the complexity that comes along with setting up an integration test.

Update: Spring 4.3 will perform implicit injection in single-constructor scenarios, making your code more independent of Spring by potentially not requiring an @Autowired annotation at all.


#### Spring boot bean scope
singleton scope
prototype scope
request scope
session scope
application scope
websocket scope
Custom thread scope

### AOP for logging


Have you used Spring data JPA,	How to mask data from Spring data JPA query results? 

### Spring data JPA v.s. Hibernate!




Spring Security features in previous project


10.	What does it mean to authenticate the RESTful request?!





#### How do you handle Restful API security?

#### How to achieve security features in the project?


#### How to improve the performance of a slow restful API?!
1. Use caching. caching data that is frequently used and same response.
2. Compressed Data. it is better to send compressed data as response. At the client end, all you need to do is to use Accept-Encoding header as gzip
3. Enable Partial Responses. do it when design
4. PATCH vs PUT. PUT would require the whole data to be sent to the REST server. If the requirement at client end is to update only a small subset of the REST resource, it is advisable to use a PATCH command so that network bandwidth is not eaten up by tons of requests reaching the server.

#### Have you used Spring data JPA, 7.	How to mask data from Spring data JPA query results?

#### Spring data JPA v.s. Hibernate
 












#### How do you test your APIs?







aws services you used before!w


# AWS
### SQS SNS
















