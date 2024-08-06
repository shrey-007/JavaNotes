### What are different Memory storages available with JVM?
1. Class(Method) Area: stores class-level data of every class such as the runtime constant pool, field, and method data, and the code for methods.
2. Heap: Objects are created or objects are stored. It is used to allocate memory to objects during run time.
3. Stack: stores data and partial results which will be needed while returning value for method and performing dynamic linking
4. Program Counter Register: stores the address of the Java virtual machine instruction currently being executed.
5. Native Method Stack: stores all the native methods used in the application.

### What is classloader
Classloader is the part of JRE(Java Runtime Environment), during the execution of the bytecode or created .class file classloader is responsible for dynamically loading the java classes and interfaces to JVM(Java Virtual Machine). Because of classloaders Java run time system does not need to know about files and file systems.

### What will happen if we declare don’t declare the main as static?
We can declare the main method without using static and without getting any errors. But, the main method will not be treated as the entry point to the application or the program.

###  Differentiate between instance and local variables
| Instance Variable                             | Local Variable                             |
|-----------------------------------------------|--------------------------------------------|
| Declared outside the method, directly invoked by the method. | Declared within the method.              |
| Has a default value.                          | No default value.                          |
| It can be used throughout the class.          | The scope is limited to the method.        |

### What is a Class Variable?
In Java, a class variable (also known as a static variable, kiuki voh object par depend nhi krte,static variables class ki property hoti hai) is a variable that is declared within a class but outside of any method, constructor, or block. Class variables are declared with the static keyword, and they are shared by all instances (objects) of the class as well as by the class itself.

### What are FilterStreams?
Stream filter or Filter Streams returns a stream consisting of the elements of this stream that match the given predicate. While working filter() it doesn’t actually perform filtering but instead creates a new stream that, when traversed, contains the elements of initial streams that match the given predicate.

### What is printf
Using it, we can use format identifiers

### What is covariant return type
Covariant return type in Java is a feature that allows an overriding method in a subclass to return a more specific type (a subtype) than the return type declared in the method of the superclass.  
Like if there is class A(parent) and B(child). Both have same function func() but the return type of func() of A is List and return type of func() of B is ArrayList.

### Difference between sleep() and wait()
| Sleep()                             | Wait()                                     |
|-----------------------------------------------|--------------------------------------------|
| The sleep() method belongs to the thread class. | Wait() method belongs to the object class. |
| Sleep does not release the lock that the current thread holds.                        | wait() release the lock which allows other threads to acquire it.|
| Mainly used to delay a thread for some specific time duration.       | Mainly used to pause a thread until notified by another thread.|

### What is jagged array
2d array with different sized rows {{1}{1,2,3}{1,2}}

### Is it possible to make an array volatile?
In Java, it is not possible to make a volatile. Volatile keywords in Java can only be applied to individual variables but not to arrays or collections. The value of the Variable is always read from and written to the main memory when it is defined as volatile rather than being cached in a thread’s local memory. This makes it easier to make sure that all threads that access the variable can see changes made to it.

### How is the ‘new’ operator different from the newInstance() method in Java?
the new operator is used to create objects, but if we want to decide the type of object to be created at runtime, there is no way we can use the new operator. In this case, we have to use the newInstance() method.

### What are the different ways to create objects in Java?
Methods to create objects in Java are mentioned below:
1. Using new keyword
2. Using new instance
3. Using clone() method
4. Using deserialization
5. Using the newInstance() method of the Constructor class

### What happens if you don’t provide a constructor in a class?
If you don’t provide a constructor in a class in Java, the compiler automatically generates a default constructor with no arguments and no operation which is a default constructor.Means you can still create objects.

### 79. Where and how can you use a private constructor?
A private constructor is used if you don’t want any other class to instantiate the object to avoid subclassing. It is used in Singleton class

### What is a marker interface?
An Interface is recognized as an empty interface (no field or methods) it is called a marker interface. Examples of marker interfaces are Serializable, Cloneable, and Remote interfaces. They are now replaced by annotations

### In java , Multiple Inheritance is supported by Interfaces only, not by classes

### What is association,aggregation,composition in OOPS

### Can we override the static method?
No. Overriding krte time konsa method chalega vo Dynamic Method Dispatch se pata chalta hai , jis object ne function call kra uski class mai dekhege ki voh function hai ki ni, if yes toh use chala denge  else uski parent class mai dekhege ki func() hai ki nhi. Since static method ko kisi object ne call nhi kiya toh Dynamic Method Dispatch laga hi nhi paaege, isliye we can't override static method.

### Can we override the overloaded method?
Yes, since the overloaded method is a completely different method in the eyes of the compiler. Overriding isn’t the same thing at all. The decision as to which method to call is deferred to runtime.

### Can we overload the main() method?
Yes in Java we can overload the main method to call the main method with the help of its predefined calling method.

### Can we override the private methods?
private stuff are only accessible to that class only. Toh child class access nhi kr skti toh override bhi ni kr skti

### Can we change the scope of the overridden method in the subclass?
less restrictive scope laga skte hai subclass mai

### How can you avoid serialization in the child class if the base class is implementing the Serializable interface?
Serialization in the child class if the base class is implementing the Serializable interface then we can avoid it by defining the writeObject() method and throwing NotSerializableException().

### Why can’t we create a generic array?
Generic arrays can’t be created because an array carries type information of its elements at runtime because of which during runtime it throw ‘ArrayStoreException’ if the elements’ type is not similar. Since generics type information gets erased at compile time by Type Erasure, the array store check would have been passed where it should have failed.

### What is Set in the Java Collections framework and list down its various implementations?
Sets are collections that don’t store duplicate elements. They don’t keep any order of the elements. The Java Collections framework provides several implementations of the Set interface, including:

1. HashSet: HashSet in Java, stores the elements in a has table which provides faster lookups and faster insertion. HashSet is not ordered.
2. LinkedHashSet: LinkedHashSet is an implementation of HashSet which maintains the insertion order of the elements.
3. TreeSet: TreeSet stores the elements in a sorted order that is determined by the natural ordering of the elements or by a custom comparator provided at the time of creation.

### What is EnumSet?
Enum is a class used to store constant varaibles. EnumSet store unique constant variables

### What is an enumeration?
Enumeration is a user-defined data type. It is mainly used to assign names to integral constants, the names make a program easy to read and maintain. The main objective of the enum is to define user-defined data types  
Like jaise baar baar 6.023*10^23 likhne se achaa use enumeration mai AVOGADRO NUMBER se deote kr skte hai

### Difference between Collection and Collections
| Collection                          | Collections                                                     |
|----------------------------------------------|-----------------------------------------------------------------|
| The Collection is an Interface.| Collections is a class.|
| It provides the standard functionality of data structure.|It is to sort and synchronize the collection elements.|
| It provides the methods that can be used for the data structure.| It provides static methods that can be used for various operations.|

###  What is the difference between Iterator and ListIterator?
Iterator can traverse all Collection, but only in forward direction.It can't modify/replace/add elements   
ListIterator can only be used to traverse list both in forward and backward direction.It can add/replace/modify list items.

### Differentiate between HashMap and HashTable.
Hashmap is not synchronized, HashTable is.

### What is the difference between Iterator and Enumeration?
Iterator-: The Iterator can traverse both legacies as well as non-legacy elements,The Iterator can perform a remove operation while traversing the collection.  
Enumeration-:Enumeration can traverse only legacy elements,The Enumeration can perform only traverse operations on the collection.

### Is it necessary that each try block must be followed by a catch block?
No, It is not necessary to use catch block after try block in Java as we can create another combination with finally block. Finally is the block which runs despite the fact that the exception is thrown or not

### What is exception propagation?
Exception propagation is a process in which the exception is dropped from to the top to the bottom of the stack. If not caught once, the exception again drops down to the previous method, and so on until it gets caught or until it reaches the very bottom of the call stack

### How do exceptions affect the program if it doesn’t handle them?
Exceptions are responsible for abruptly terminating the running of the program while executing and the code written after the exception occurs is not executed.

### What is the difference between this() and super() in Java?
| Feature                              | `this`                                       | `super`                                   |
|--------------------------------------|----------------------------------------------|-------------------------------------------|
| Calls default constructor            | Calls the default constructor of the same class. | Calls the default constructor of the base class. |
| Represents                           | Represents the current instance of the class. | Represents the current instance of the parent class. |
| Access methods                       | Accesses the methods of the same class.       | Accesses the methods of the parent class. |
| Points to                            | Points to the current class instance.         | Points to the superclass instance.        |

### Life cycle of a thread
A thread in Java at any point in time exists in any one of the following states. A thread lies only in one of the shown states at any instant:

1. New: The thread has been created but has not yet started.
2. Runnable: The thread is running, executing its task, or is ready to run if there are no other higher-priority threads.
3. Blocked: The thread is temporarily suspended, waiting for a resource or an event.
4. Waiting: The thread is waiting for another thread to perform a task or for a specified amount of time to elapse.
5. Terminated: The thread has completed its task or been terminated by another thread.










