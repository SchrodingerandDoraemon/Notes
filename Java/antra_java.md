### Protected vs public
Protected can be declared for Variables, methods, and constructor, it makes can be accessed only by the subclasses in other package or any class within the package. The protected access modifier cannot be applied to class and interfaces.\
The public keyword is an access modifier used for classes, attributes, methods and constructors, making them accessible by any other class

### final in local variable
final class: can not extent the class
final variable: no change
final method: no override

### Deep copy VS shallow copy
shallow copy only copy the references of those objects. One object, two reference.
Deep copy means a new object will be created, and all the values of original object will be copied to the new object. Two object, two reference. We have to override the clone() method to use deep copy.
 
### ConcurrentHashMap
ConcurrentHashMap class is thread-safe. It works by dividing complete hashtable array into segments or portions and allowing parallel access to those segments. The locking is at a much finer granularity at a hashmap bucket level(all methods are synchronized on Hashtable instances using the synchronized keyword). ConcurrentHashMap does not allow NULL values, so the key can not be null in ConcurrentHashMap.

If a thread-safe highly-concurrent implementation is desired, then it is recommended to use ConcurrentHashMap in place of Hashtable.

### Synchronized HashMap
It locks the whole map.performance of ConcurrentHashMap is relatively better than the Synchronized Map. Synchronized HashMap allows inserting null as a key. ConcuurentHashMap doesn’t allow inserting null as a key or value.

### referency data type
Reference datatypes in java are those which contains reference/address of dynamically created objects. These are not predefined like primitive data types.

Following are the reference types in Java.

1. class types − This reference type points to an object of a class.

2. array types − This reference type points to an array.

4. interface types − This reference type points to an object of a class which implements an interface.

Once we create a variable of these types (i.e. when we create an array or object, class or interface).

1. These variables only store the address of these values.

2. Default value of any reference variable is null.

3. A reference variable can be used to refer any object of the declared type or any compatible type.

### static method and default method introduced in Java 8
They are used to create a common feature/action for the class implantate them. 

Static method in interface means we can directly use the method by use the interface.method

default methods which allow the interfaces to have methods with implementation.

### Switch
two point to memorize:
1. use break. Without break, it will continue execute to the next case. 
2. default statement is used when none of the cases is true.

### access modifer is used for encapsulation
default: in package
protected: subclass in other package or within the package

### Final
change the final reference is a checked exception.

### immutable class
An immutable class is simply a class whose instances cannot be modified. 
e.g. String, Integer...

### how to customize our own immutable class
1. Declare the class as final so it can’t be extended.
2. Make all fields private so that direct access is not allowed.
3. Don’t provide setter methods for variables.
4. Make all mutable fields final so that its value can be assigned only once.
5. Initialize all the fields via a constructor performing deep copy(with getter method).
6. Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

### Memory area (it is the logical way)
1.Class(Method) Area: It stores class level data of every class such as the runtime constant pool, field and method data, the code for methods.
2.Heap
3. Stack
4. Program Counter Register
5. Native Method Stack

### Junit 4.0
Unit is the testing framework, it is used for unit testing of Java code. JUnit = Java + Unit Testing  

The process of testing individual functionality (known as a unit) of the application is called unit testing.

### Maven
Maven is a project management tool. It provides the developer a complete build lifecycle framework. On executing Maven commands, it will look for POM file in Maven; it will run the command on the resources described in the POM.

POM
POM (Project Object Model) is the fundamental unit of work. It is an XML file which holds the information about the project and configuration details used to build a project by Maven.

Explain what is Maven artifact?
Usually an artifact is a JAR file which gets arrayed to a Maven repository. One or more artifacts a maven build produces such as compiled JAR and a sources JAR.

Explain what is Maven Repository? What are their types?

A Maven repository is a location where all the project jars, library jars, plugins or any other particular project related artifacts are stored and can be easily used by Maven.

### JDK/JRE/JVM
the relation of subset
JDK: JRE + dev tools
JRE = JVM + java SE stardard librart
JVM = stands for Java Virtual Machine, is a virtual machine that understands and runs java bytecodes.

### Java hotspot
What Is HotSpot? HotSpot, also called Java HotSpot Virtual Machine, or HotSpot JVM, is an implementation of the JVM (Java Virtual Machine) Specification originallly developed by Sun Microsystems and now supported by Oracle Corporation.

HotSpot has key feature called adaptive compiler that application code will be analyzed as it runs to detect performance bottlenecks, or "hot spots". HotSpot will then compile those hot spots for a boost in performance.

### why java is not a pure object oriented language?
because it supports primitive data type

### autobox / unboxing
Autoboxing is the automatic convert primitive types to their corresponding object wrapper classes.
unboxing is the automatic convert object wrapper classes to their corresponding primitive types.

### Interface vs Abstract class 
1. Interface can do multi-inheritance.
2. Final Variables: Variables declared in interface are by default final. An abstract class may contain non-final variables.
3. Accessibility of Data Members: Members of a Java interface are public by default. A Java abstract class can have class members like private, protected, etc.

### class loader
Class loaders are responsible for loading Java classes during runtime dynamically to the JVM.  Also, they are part of the JRE.
***bootstrap or primordial class loader*** loads the java.lang.ClassLoader itself. It's mainly responsible for loading JDK internal classes. This bootstrap class loader is part of the core JVM and is written in native code.

The ***extension class loader*** is a child of the bootstrap class loader and takes care of loading the extensions of the standard core Java classes so that it's available to all applications running on the platform.

***application class loader***loads all the application level classes into the JVM. It loads files found in the classpath environment variableAlso, it's a child of Extensions classloader.

![image](https://user-images.githubusercontent.com/35554521/146659820-85a60803-d9f5-4534-8e3e-1fd117a3fb20.png)

### Where is constant string pool
in heap memory. Constant string pool stores literal string values.

### Method area
In the method area, all class level information like class name, immediate parent class name, methods and variables information etc. are stored, including static variables.

### static
static method and static variable are in method area. method area are in the metaspce.

### reference data type consists of reference and object

### throw 
two purpose:
1. tell the programmar 
2. used for custom exception

### final, Finally, finally.
The final keyword can be used with class method and variable. A final class cannot be inherited, a final method cannot be overridden and a final variable cannot be reassigned.

The finally,used in try-catch, whatever exception happened or not, the finally block will excuted. Using a finally block allows you to run any cleanup-type statements to realse to resource. System exit can interrupt the finally

finalize() method of Object class is a method that the Garbage Collectoralways calls just before the destroying the object which is eligible for Garbage Collection, so as to perform clean-up activity. Clean-up activity means closing the resources associated with that object like Database Connection, Network Connection or we can say resource de-allocation. Remember it is not a reserved keyword. Once the finalize method completes immediately Garbage Collector destroy that object.

### Error 
stackoverflow is error

###
