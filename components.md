1. In languages like c pehele code compile hoga(conversion of c code to assembly code). Fir assembly code ko assembler 0/1 mai convert krke intstruction bhejega. Assembly code is machine dependent, toh Agar m1 machine mai code likha and vaha complile kara toh vaha m1 ka assembly code mai compile hua hai, us compiled code ko tum m2 mai dekar nhi chala skte
2. In Java, javac is compiler which converts source code(.java) to byte code(.class). This byte code is machine independent toh ye kisi bhi machine mai chalega. Now JVM(interpreter) executes byte code line by line. Every OS has different JVM. So java is both compiled and interpreted.

### Components-:
1. javac is included in JDK(isko ese yaad rakho JDK is development kit, jo log develop krte hai java program unhe JDK chaiye hota hai.Baaki jinhe sirf run krna hai unhe JRE se bhi kaam chal jaaega, since run krne mai compiler ki need nhi hoti JVM ki need hoti hai isliye JRE mai compiler nhi hota. Development mai code khud se likhoge toh compile kroge usme compiler ki need hogi isiye JDK mai compiler hota hai.)
2. JDK is complete kit that contains compiler,JRE,debuggers,java docs.
3. JRE is used to run java program. It includes JVM
4. Garbage Collector to delete unreferenced objects. It is inside JVM
5. ClassPath is the file path jaha saari .class files hoti hai, toh JVM vahi execute krta hai. If you want to add extra libraries then you need to add them in classpath
6. JVM,JRE,JDK are platform dependent, Byte code is platform independent
7. Toh basically JDK contains JRE, javac and some development tools.JRE contains JVM and some extra libraries.JVM contains Garbage collector.  
JDK &rarr; JRE, javac, tools  
JRE &rarr; JVM and libraries  
JVM &rarr; garbage collector, JIT
8. If you just need to run the java executable file(java app) then you just need JRE. JDK is used by developers only.
9. JVM is the one that actually calls the main method in java code
10. Since JVM runs java program toh JVM ke under hi heap and stack hota hai.
11. Important ye hai ki stack function ki nhi thread ki bnti hai.
12. JIT(Just In Time Compiler) is one of the component of JVM which increases its performance.

### Memory Allocation in Java
1. Stack-: It allocates/deallocates memory as corresponding method is executed.Data in stack can only be accessed by the owner thread, so it is thread safe. It is faster. Less Space hota hai isliye Stack overflow jyaada aata hai.
2. Heap-: Allocates memory when new keyword is used, and deallocates using garbage collector. It is not thread safe. It takes more time to access objects in heap. Space is large.

### Garbage Collector
1. Example of daemon thread
2. Removes unreferenced objects
3. JVM runs garbage collector, humara uspr control nhi hai, however we can call System.gc() to request garbage collector to work, but vo JVM ka hi decission hai ki request accept krega ki nhi
4. Before destroying the object, it calls finalize() method to perform cleanup activities. finalize() method is empty , so we can override it and perform specific operation according to our need before deleting the object
5. Jab heap memory bhar jaati hai toh usko Memory leak kehte hai.
