### Protected vs public
Protected can be declared for Variables, methods, and constructor, it makes can be accessed only by the subclasses in other package or any class within the package. The protected access modifier cannot be applied to class and interfaces.\
The public keyword is an access modifier used for classes, attributes, methods and constructors, making them accessible by any other class

### how to customize our own immutable class
1. Declare the class as final so it can’t be extended.
2. Make all fields private so that direct access is not allowed.
3. Don’t provide setter methods for variables.
4. Make all mutable fields final so that its value can be assigned only once.
5. Initialize all the fields via a constructor performing deep copy(with getter method).
6. Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.

### final in local variable

### Deep copy VS shallow copy
shallow copy only copy the references of those objects
Deep copy means a new object will be created, and all the values of original object will be copied to the new object.

### ConcurrentHashMap
ConcurrentHashMap class is thread-safe. It works by dividing complete hashtable array into segments or portions and allowing parallel access to those segments. The locking is at a much finer granularity at a hashmap bucket level(all methods are synchronized on Hashtable instances using the synchronized keyword). ConcurrentHashMap does not allow NULL values, so the key can not be null in ConcurrentHashMap.

If a thread-safe highly-concurrent implementation is desired, then it is recommended to use ConcurrentHashMap in place of Hashtable.

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

### 
