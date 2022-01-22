### JavaEE and Spring difference
Spring doesn't implement JavaEE specifications.


## Three Layer Architecture
<img width="1205" alt="image" src="https://user-images.githubusercontent.com/35554521/149875086-b7a8d83b-15a1-470a-8c49-2afdbd35e2f0.png">
decouple -- losely coupled -- easy for maintainance and update 

### URL components
URI = scheme ":" ["//" authority] path ["?" query] ["#" fragment]

A fragment is an internal page reference, sometimes called a named anchor. It usually appears at the end of a URL and begi ns with a hash (#) character followed by an identifier. It refers to a section within a web page.

In HTML documents, the browser looks for an anchor tag with a name attribute matching the fragment.

## Spring is a light wight, open source JavaEE frameworks
Core parts: IOC and Aop(Aspect-oriented programming)

Aop: It does so by adding additional behavior to existing code (an advice) without modifying the code itself

### IOC and Dependency injection
Spring container primary functions:
- Create and manage objects(IOC)
- Inject object's dependencies ()

Two common types of injection
- constructor injection
- setter injection
- auto-wiring  

Constructor injection steps:
1. define the dependecy interface and class
2. create a constructor in your class for injections
3. configure the dependency injection in spring config file

Setter injection steps;
1. Create setter methods in your class for injections.
2. Configure the dependecy injection in Spring config file.

### Spring development process
1. configure Spring beans
2. create a Spring container
3. Retrieve Beans from Spring container
4. call methods on the bean
5. close the context

Spring container is generically known as ***ApplicationContext***

Spring container specialized implementations
- ClassPathXmlApplicationContext
- AnnotationConfigApplicationContext
- GenericWebApplicationContext
- others...

### Default scope of Spring bean is singleton  
scope refer tot the life cycle of a bean.
singleton instance cached in memory 
prototype, request, session, global session

<img width="1401" alt="image" src="https://user-images.githubusercontent.com/35554521/150617899-7b77f8b0-bba0-43f5-8c05-c670b8957cb1.png">

#### Special Note: Defining init and destroy methods - Method Signatures
Special Note about init and destroy Method Signatures

When using XML configuration, I want to provide additional details regarding the method signatures of the init-method  and destroy-method .

Access modifier
The method can have any access modifier (public, protected, private)

Return type
The method can have any return type. However, "void' is most commonly used. If you give a return type just note that you will not be able to capture the return value. As a result, "void" is commonly used.

Method name
The method can have any method name.

Arguments
The method can not accept any arguments. The method should be no-arg.



# QA
1. FAQ: What is a Spring Bean?

A "Spring Bean" is simply a Java object.

When Java objects are created by the Spring Container, then Spring refers to them as "Spring Beans".

Spring Beans are created from normal Java classes .... just like Java objects.'

Offical definition:
In Spring, the objects that form the backbone of your application and that are managed by the Spring loC container are
called beans. A bean is an object that is instantiated, assembled, and otherwise managed by a Spring loC container.
Otherwise, a bean is simply one of many objects in your application. Beans, and the dependencies among them, are
reflected in the configuration metadata used by a container.

2. Why do we specify the interface in getBean()
```
Coach theCoach = context.getBean("myCoach", Coach.class); 
```
Compared to the previous method(Tiger tiger = (Tiger) context.getBean("lion") ), this one is safer because we get the information about type mismatch instantly:

3.  What is the purpose for the no arg constructor in Spring 
When you don’t define any constructor in your class, compiler defines default one for you, however when you declare any constructor (in your example you have already defined a parameterized constructor), compiler doesn’t do it for you.

Since you have defined a constructor in class code, compiler didn’t create default one. While creating object you are invoking default one, which doesn’t exist in class code. Then the code gives an compilation error.

hibernate, creates an instance of entities using reflection it uses the Class.newInstance() method, which requires a no-argument constructor to create an instance. It's effectively equivalent to the new Entity(). 

Spring create a instance by calling no argument constructor and then use setter injection to provided dependency.



