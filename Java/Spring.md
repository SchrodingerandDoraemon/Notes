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
- field injection (use reflection)
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

For "prototype" scoped beans, Spring does not call the destroy method.  Gasp!  


In contrast to the other scopes, Spring does not manage the complete lifecycle of a prototype bean: the container instantiates, configures, and otherwise assembles a prototype object, and hands it to the client, with no further record of that prototype instance.

Thus, although initialization lifecycle callback methods are called on all objects regardless of scope, in the case of prototypes, configured destruction lifecycle callbacks are not called. The client code must clean up prototype-scoped objects and release expensive resources that the prototype bean(s) are holding. 

This also applies to both XML configuration and Annotation-based configuration. For "prototype" scoped beans, Spring does not call the @PreDestroy method.  Gasp!  

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




# Spring MVC
Front controller known as DispatcherServlet

<img width="1347" alt="image" src="https://user-images.githubusercontent.com/35554521/150625092-a04bdf93-82f4-483a-afe9-be542250b025.png">

<img width="1313" alt="image" src="https://user-images.githubusercontent.com/35554521/150625209-08831981-f9c4-44b2-8887-d6eaf048ebae.png">

<img width="1306" alt="image" src="https://user-images.githubusercontent.com/35554521/150625215-5f4f5483-6ed7-4dcf-bd82-ffe524388ffa.png">

<img width="1317" alt="image" src="https://user-images.githubusercontent.com/35554521/150625240-7f1e7dbb-7a55-4c7c-9520-7f6ecec099bb.png">



href: Hypertext REFerenc














--

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

4.  special case of when BOTH the first and second characters of the class name are upper case, then the name is NOT converted.

For the case of RESTFortuneService

RESTFortuneService --> RESTFortuneService


5. FAQ: What is a real-time use case for @Bean?
Here is a real-time use case of using @Bean: You can use @Bean to make an existing third-party class available to your Spring framework application context.

For example, I was recently working on a global real-time project using Amazon Web Services. The project made use of the Amazon Simple Storage Service (AWS S3). This is remote service that provides object storage in the cloud. You can think of AWS S3 at a high-level as a remote file server for storing files (pdfs, pngs etc).

Our Spring application needed to integrate with AWS S3 and store pdf documents. Amazon provides an AWS SDK for integrating with AWS S3. Their API provides a class, S3Client. This is a regular Java class that provides a client interface to the AWS S3 service. We needed to share the S3Client object in various services in our Spring application. However, the S3Client does not have the @Component annotation. The S3Client does not use Spring.

Since the S3Client is part of the AWS framework, we can't modify the source code for the S3Client directly. We can't simply add the @Component annotation to the S3Client source code. As a result, we need an alternative solution.

But no problem, by using the @Bean annotation, I can wrap this third-party class, S3Client, as a Spring bean. And then once it is wrapped using @Bean, it is as a singleton object and available in our Spring framework application context. I can now easily share this bean in my app using dependency injection and @Autowired. So think of the @Bean annotation was a wrapper / adapter for third-party classes. You want to make the third-party classes available to your Spring framework application context.



Here's a real-time example

Here is a snippet from our @Configuration class. We create an instance of the S3Client and wrap it as a Spring bean. The default scope is singleton. It is now available in our application context and we can inject it to other parts of our Spring application using @Autowired.

    @Bean
    public S3Client remoteClient() {
        
            // Create an S3 client to connect to AWS S3
            S3Client s3Client = S3Client.builder().region(Region.of(region))
                    .credentialsProvider(StaticCredentialsProvider.create(awsCreds)).build();
     
            return s3Client;    
    }




---

In the code below, this is a Spring service that uses the S3Client. The service @Service annotation is a subclass of @Component. This code uses @Autowired to inject the bean named "remoteClient". This bean was created in the configuration code above using @Bean.

Once the bean is injected, then our method can use this to interact with the Amazon S3 service. In this real-time project, we were processing insurance claims. We store the PDF invoices in the cloud using the AWS S3 service.

    @Service
    public class InsuranceClaimsServiceImpl implements ClaimsService {
        
        @Autowired
        private S3Client remoteClient;
     
        ...
     
        public void processClaim(Claim theClaim) {
     
     
            // read claim data
            FileData fileData = theClaim.getFileData("payerInvoice");
            String fileName = theClaim.getSubmittedFileName();    
     
            // get the input stream and file size
                InputStream fileInputStream = fileData.getInputStream();
                    long contentLength = fileData.getSize();
     
                //
            // store claim data in AWS S3 
            //
     
            // Create a put request for the object
            PutObjectRequest putObjectRequest = PutObjectRequest.builder()
                                .bucket(bucketName)
                                .key(subDirectory + "/" + fileName)
                                .acl(ObjectCannedACL.BUCKET_OWNER_FULL_CONTROL).build();
            
            // perform the putObject operation to AWS S3 ... using our autowired bean
            remoteClient.putObject(putObjectRequest, RequestBody.fromInputStream(fileInputStream, contentLength))
        }
    }


As you can see, I was able to wrap a third-party class as a Spring bean. The AWS S3Client object was not originally annotated with @Component. The S3Client is not aware of Spring. But I could manually wrap it using @Bean. By doing this, the object is now available in our Spring application context. We can now share/reuse this bean in other areas of our Spring app by using dependency injection and @Autowired.

For other services in our application, if they need access to the S3client (singleton) then they can simply inject it using @Autowired. No need for each service to create a new instance of the S3Client every time. This keeps the application efficient in terms of memory and performance.

---

In summary: You can use @Bean to make an existing third-party class available to your Spring framework application context.



Note: You can use both two approaches of @Bean AND component scanning depending on your application requirements. You can use @Bean for third-party beans. For your existing beans in your class you can use component scanning with @Component (also @Controller, @Service, @Repository ...).



