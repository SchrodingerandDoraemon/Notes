### REST api
An ***aspect*** is a modularization of a concern that cuts across multiple classes

***RESTFUL*** is referred for web services written by applying REST architectural concept are called RESTful services, it focuses on system resources and how state of resource should be transported over HTTP protocol to different clients written in different language. In RESTFUL web service HTTP methods like GET, POST, PUT and DELETE can be used to perform CRUD operations.

The architectural style for creating web api are
- HTTP for client server communication
- XML/JSON as formatting language
- Simple URI as the address for the services
- Stateless communication

HTTP methods supported by REST are:
- GET: It requests a resource at the request URL. It should not contain a request body as it will be discarded. Maybe it can be cached locally or on the server.
- POST: It submits information to the service for processing; it should typically return the modified or new resource
- PUT: At the request URL it update the resource
- DELETE: At the request URL it removes the resource
- OPTIONS: It indicates which techniques are supported
- HEAD: About the request URL it returns meta information

Some key characteristics of REST includes
- REST is stateless which means the client request and response are not dependent on others and thereby provides total assurance of getting the required data.
- With a well-applied REST API, the server could be restarted between two calls as every data is passed to the server
- Web service mostly uses POST method to make operations, whereas REST uses GET to access resources


The disadvantages of RESTful web services:
- As the services follow the idea of statelessness, it is not possible to maintain sessions. (Session simulation responsibility lies on the client-side to pass the session id)
- REST does not impose security restrictions inherently. It inherits the security measures of the protocols implementing it. Hence, care must be chosen to implement security measures like integrating SSL/TLS based authentications, etc.


Resources are identified by logical URLs; it is the key element of a RESTful design. Unlike, SOAP web services in REST, you view the product data as a resource and this resource should contain all the required information.

Do not use "physical" URLs. A physical URL points at something physical -- e.g., an XML file: "http://www.acme.com/inventory/product003.xml". A logical URL does not imply a physical file: "http://www.acme.com/inventory/product/003"

Statelessness means that every HTTP request happens in complete isolation. When the client makes an HTTP request, it includes all information necessary for the server to fulfill the request. The server never relies on information from previous requests from the client.

URL stands for Uniform Resource Locator. URI stands for Uniform Resource Identifier. URL is a subset of URI that specifies where a resource is exists and the mechanism for retrieving it.

The medium of communication between the client and server is called “Messaging”, like HTTP response and HTTP request. The messages contained constitute the data and the metadata about the message.

Resources are accessible to the service by means of URIs.






1) Mention what tools are required to test your web API?
SOAPUI tool for SOAP WS and Firefox “poster” plugin for RESTFUL services.

2) Mention whether you can use GET request instead of PUT to create a resource?
No, you are not supposed to use PUT for GET. GET operations should only have view rights, while PUT resource is used for updating a data.

3) Mention what is the difference between PUT and POST?

“PUT” puts a file or resource at a particular URI and exactly at that URI. If there is already a file or resource at that URI, PUT changes that file or resource. If there is no resource or file there, PUT makes one

POST sends data to a particular URI and expects the resource at that URI to deal with the request. The web server at this point can decide what to do with the data in the context of specified resource

PUT is idempotent meaning, invoking it any number of times will not have an impact on resources.

However, POST is not idempotent, meaning if you invoke POST multiple times it keeps creating more resources.



4) Mention which markup language can be used in restful web api?

JSON and XML are the two markup language that can be used in restful web api

5) List out the tools or API for developing or testing web api? Testing tools for web services for REST APIs includes

Spring REST web service using MVC
Jersey API
CXF
Axis
Restlet,



### DAO, DTO
DTO is an abbreviation for Data Transfer Object, so it is used to transfer the data between modules of your application. DTO should only contain private fields for your data, getters, setters, and constructors. DTO will be passed as value object to DAO layer and DAO layer will use this object to persist data using its CRUD operation methods.

DAO is an abbreviation for Data Access Object, so it should encapsulate the logic for CRUD operation in your data storage (a database, a file-system, whatever).



### notify vs notifyAll
notify() sends a notification to one waiting thread, notifyAll() sends a notification to all waiting threads

### hashcode equals



Coding: fibonacci








经常会被问到spring配置文件的细节问题，如何配置，spring 安全如何配置，profile这种😭
rest api也会让我手写

诸如什么是immutable class，怎么implemement，或是Java 8里为什么用Optional这类的问题。
