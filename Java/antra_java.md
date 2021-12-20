### Protected vs public
Protected can be declared for Variables, methods, and constructor, it makes can be accessed only by the subclasses in other package or any class within the package. The protected access modifier cannot be applied to class and interfaces.\
The public keyword is an access modifier used for classes, attributes, methods and constructors, making them accessible by any other class

protected and private can not be used with class, which means they can only be used to method and variable.

class can only be default class or public class

Interface are by default public.

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
1.Class(Method) Area: It stores class level data of every class such as the runtime constant pool, field and method data, the code for methods, Static block
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
JVM = stands for Java Virtual Machine, is a virtual machine that understands and runs java bytecodes. JVM has the memory structure is the explicit difference from normal VM.

### Java hotspot
What Is HotSpot? HotSpot, also called Java HotSpot Virtual Machine, or HotSpot JVM, is an implementation of the JVM (Java Virtual Machine) Specification originallly developed by Sun Microsystems and now supported by Oracle Corporation.

HotSpot has key feature called adaptive compiler that application code will be analyzed as it runs to detect performance bottlenecks, or "hot spots". HotSpot will then compile those hot spots for a boost in performance.

### why java is not a pure object oriented language?
because it supports primitive data type

### casting
implicit casting: coverting without losing data. e.g. int ---> double

explicit casting: Coverting with losing data. 

Down casting: form superclass to subclass  --- explicitly

Up casting: from subclass to a superclass ---> implicity

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

The ***extension class loader*** is a child of the bootstrap class loader and are reponsible for loading the extensions of the standard core Java classes so that it's available to all applications running on the platform. It loads the jar package.

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

### thread
Thread share method area and heap, but each thread have their own stack, PC register and native method stack.

Thread safe is about reference.

### why to override hashcode() and equals()
If we override the equals(), then we have to override hashcode(). Otherwise, it could cause some problems for hash based data structures. For example, the same object value would have different hash value, then they woule both be added to the hashmap, then the keys would be duplicate. The Reverse is not true, it would cause any troubles, but it's the convention and best pratice to override them both. I will override them both.

### Hashset
Hashset internally use HashMap. It takes the keys as its elements, but set the values to be null always.

Sets.intersection(a,b) / Sets.Union(a, b) / set1.removeAll(set2)

### Integer
Integer cache values from –128 to +127. 

### == equal equal sign

### Vector
Vector is also a dynamic array. Vector is synchronized. vector increments 100% of the current array size if the number of elements exceeds its capacity. Arraylist is preferred than vector.

### comparator / comparable
We create a create a Comparator object to use comparetor, override comare() in comparator interface. we use comparable by implement a comparable interface, and override the compareTo() 

The Comparable interface is a good choice to use for defining the default ordering, or in other words, if it's the main way of comparing objects.

### So why use a Comparator if we already have Comparable?
1. Sometimes we can't modify the source code of the class whose objects we want to sort.
2. Using Comparators allows us to avoid adding additional code to our domain classes
3. We can define multiple different comparison strategies, which isn't possible when using Comparable

### Static block
A static block run once for each time a class is loaded into memory. It's stored in method area.

### Throws vs Throw
Throws clause is used to declare an exception in the method signature, which means it works similar to the try-catch block. The exception of throws in superclass have to be the superclass of exception of throws in subclass。

Throw keyword is used to throw an exception explicitly in the method body.

### Serializable
Serialization is the process of turning an object in memory into a stream of bytes so you can do stuff like store it on disk or send it over the network.

Deserialization is the reverse process: turning a stream of bytes into an object in memory.

implement Serializable interface ---> FileOutputStream ---> ObjectOutputStream

#### What is need of Serialization?
Answer:
Serialization is usually used when there is need to send your data over network or to store in files. By data I mean objects and not text.

Now the problem is your Network infrastructure and your Hard disk is hardware components that understand bits and bytes but not Java objects.

Serialization is the translation of Java object’s values/states to bytes to send it over network or to save it.On the other hand, Deserialization is conversion of byte code to corresponding java objects.

Serializable is marker interface.Marker interface in Java is interfaces with no field or methods or in simple word empty interface in java is called marker interface.

#### Can you Serialize static variables?
Answer :
No,you can’t.As you know static variable are at class level not at object level and you serialize a object so you can’t serialize static variables.

#### How can you avoid certain member variable of class to be serialized?
You can mark that variable as either static or transient. Let’s see a simple example using transient variable.
Transient variable is the variable whose value is not serialized during serialization. You will get default value for these variable when you deserialize it.

#### What  if superclass is Serializable?  Does that mean child class is automatically Serializable?
Answer : Yes. If you don’t want subclass to serializable then you need to implement writeObject() and readObject() method and need to throw NotSerializableException from this methods.

### Java double lose precision
Use BigDecimal.  -- > bigDecimal1.subtract(bigDecimal2)

x^2 / x to the power of 2 is always accurate.

### String[] args
args stands for the name of String array. The parameter of main method can not be changed

### There is no static local variable

### volatile 
The Java volatile keyword is used to mark a Java variable as "being stored in main memory". So any changes to the variable areacross threads.

### Enum
Enum is the lists of constants. 

Q: Can Enum constants can be declared as static and final?
A: Yes. Enum constants are public static and final and are accessible directly using enum name.

Q: Can a constuctor be invoked using an Enum?
A: Yes we can use the constuctor with the name of Enum.

Q: Can we extend an Enum to add elements?
A: No, we cannot extend Enum further in the Code. It is defined only with keyword Enum and filled with elements but these elements cannot be added further in the program using some alternative method.

Q: Can we create object of Enum?
A: No, it is not possible to create the object of Enum.

Q: Can Enum implement an interface in Java?
A: Yes, Enum can implement an interface in Java. Since enum is a type, similar to class and interface, it can implement an interface. This gives a lot of flexibility to use Enum as a specialized implementation in some cases. You can further see here an example of Enum implementing an interface in Java.

### @Retention and Annotation
@inherited is a type of meta-annotation used to annotate custom annotations so that the subclass can inherit those custom annotations. 

By default, Java annotations are not shown in the documentation created using the Javadoc tool. To ensure that our custom annotations are shown in the documentation, we use @Documented annotation to annotate our custom annotations. @Documented is a meta-annotation (an annotation applied to other annotations)

Q1. What Are Annotations? What Are Their Typical Use Cases?
Annotations are metadata bound to elements of the source code of a program and have no effect on the operation of the code they operate.

Their typical uses cases are:
1. Information for the compiler – with annotations, the compiler can detect errors or suppress warnings
2. Compile-time and deployment-time processing – software tools can process annotations and generate code, configuration files, etc.
3. Runtime processing – annotations can be examined at runtime to customize the behavior of a program

Q3. How Can You Create an Annotation?
```
public @interface SimpleAnnotation {
    //whose body contains annotation type element
    String value();

    int[] types();
}
```

Q6. Is There a Way to Limit the Elements in Which an Annotation Can Be Applied?
```
@Target({ ElementType.FIELD, ElementType.METHOD, ElementType.PACKAGE })
//pass multiple constants if we want to make it applicable in more contexts
@Target({})
//it cannot be used to annotate anything
```

Q7. What Are Meta-Annotations?
Meta-Annotations? Are annotations that apply to other annotations.

All annotations that aren't marked with @Target, or are marked with it but include ANNOTATION_TYPE constant are also meta-annotations
'''
@Target(ElementType.ANNOTATION_TYPE)
public @interface SimpleAnnotation {
    // ...
}
'''

Q9. How Can You Retrieve Annotations? How Does This Relate to Its Retention Policy?
You can use the Reflection API or an annotation processor to retrieve annotations.

The @Retention annotation and its RetentionPolicy parameter affect how you can retrieve them. There are three constants in RetentionPolicy enum:

RetentionPolicy.SOURCE – makes the annotation to be discarded by the compiler but annotation processors can read them

RetentionPolicy.CLASS – indicates that the annotation is added to the class file but not accessible through reflection

RetentionPolicy.RUNTIME –Annotations are recorded in the class file by the compiler and retained by the JVM at runtime so that they can be read reflectively

Here's an example code to create an annotation that can be read at runtime:
```
@Retention(RetentionPolicy.RUNTIME)
public @interface Description {
    String value();
}
```
Now, annotations can be retrieved through reflection:
```
Description description
  = AnnotatedClass.class.getAnnotation(Description.class);
System.out.println(description.value());
```
An annotation processor can work with RetentionPolicy.SOURCE

RetentionPolicy.CLASS is usable when you're writing a Java bytecode parser.

Q10. Will the Following Code Compile?
```
@Target({ ElementType.FIELD, ElementType.TYPE, ElementType.FIELD })
public @interface TestAnnotation {
    int[] value() default {};
}
```
No. It's a compile-time error if the same enum constant appears more than once in an @Target annotation.

Removing the duplicate constant will make the code to compile successfully:
```
@Target({ ElementType.FIELD, ElementType.TYPE})
```

Q11. Is It Possible to Extend Annotations?
No. Annotations always extend java.lang.annotation.Annotation, as stated in the Java Language Specification.

If we try to use the extends clause in an annotation declaration, we'll get a compilation error:

Q12. Can one class be provided with two annotation
Yes.

### Generics
Generics mean parameterized types. The idea is to allow type to be a parameter to methods, classes, and interfaces. Using Generics, it is possible to create classes that work with different data types. 

Q2. How Generics works in Java ? What is type erasure ?\
This is one of the better interview question in Generics. Generics is implemented using Type erasure, the compiler erases all type related information during compile time and no type related information is available during runtime. for example List<String> is represented by only List at runtime. 

Q3. What Are Some Advantages of Using Generic Types?
One advantage of using generics is avoiding casts and provide type safety(compile type check), because we change the runtime exception to be a checked exception.
 
the other advantage is to avoid code duplication. Without generics, we have to copy and paste the same code but for different types. 

Q9. What Is a Wildcard Type?
A wildcard type represents an unknown type.
 
### Exception
Larger scope exception should put in the later place.
 
Custom unchecked exception extends RuntimeException.(RuntimeException is subclass of Exception) 

Custom checked exception extends exception. 
 
All excepiton are serializable, This is because the root class for all exceptions, Throwable implements the Serializable interface. All exceptions by default are serializable and that's a language design decision because the authors wanted ***exceptions to be capable of being sent across the wire without any special configuration***.
 
### mkdir()
mkdir() method is a part of File class. The mkdir() function is used to create a new directory denoted by the abstract pathname. 
 
### lambda 
contain parameter and method body, and can return any type.
 
### Method reference
Method reference is used refer method of functional interface. It is nothing but compact way of lambda expression. You can simply replace lambda expression with method reference.
```
Syntax:
class::methodname
 
object::methodname
```
 
### Imperative programming vs Declarative programming
Imperative Programming: In this, programs specify how it is to be done. 
Declarative Programming: In this, programs specify what is to be done. 

### Functional interface (means it represent functionality)
have single abstract method. 
 
It is not madatory but recommended to use @FunctionalInterface annotation to avoid the addition of extra methods accidentally.
 
consumer: consume a value and return a void
 
Supplier: supply a value
 
Function: map a value to different value
 
predicate: test a condition
 
### Stream API
#### What is the parallel Stream? How can you get a parallel stream from a List? (answer) 
A parallel stream can parallel execute stream processing tasks. For example, if you have a parallel stream of 1 million orders and you are looking for orders worth more than 1 million, then you can use a filter to do that.

Unlike sequential Stream, the parallel Stream can launch multiple threads to search for those orders on the different parts of the Stream and then combine the result.

#### What is the difference between intermediate and terminal operations on Stream? (answer)
The intermediate Stream operation returns another Stream, intermediate stream have to combined with terminal operation.
 
On the other hand, the terminal operation produces a result.

Once a terminal method like forEach() or collect() is called, you cannot call any other method of Stream or reuse the Stream.
 
#### What do you mean by saying Stream is lazy? (answer)
When we say Stream is lazy, we mean that most of the methods are defined on Java .util.stream.Stream class is lazy i.e. they will not work by just including them on the Stream pipeline.

They only work when you call a terminal method on the Stream and finish as soon as they find the data they are looking for rather than scanning through the whole set of data.
 
 ### Optional
Use optional to avoid NullPointerException.
```
Optional<object> optional1 = Optional.empty()
if(optional1.isPresent()){
   sout("it is empty")
 }
```

### Other Java
 .class is not compulsory to be the same as .java
 ```
 /*
 multiple comment 
 */
 ```
 
tenary operation --->used with return OR assignment 

JavaP:The javap tool is used to get the information of any class or interface. The javap command (also known as the Java Disassembler) covert bytecode to java code only with structure



