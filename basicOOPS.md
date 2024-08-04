### 4 pillars(A PIE)
1. Abstraction-: providing only abstraction through abstract classes and interfaces
2. Polymorphism-: Using same name of the function which serve same purpose. Achieved through Overriding and Overloading is used.
3. Inheritance-: It supports reusability of code.
4. Encapsulation-: Same as data hiding, private keyword ko use krna and variables ko access krne ke liye getters and setters use krna

- Java is not proper OOP language as it has PDT also
- We can use Parent p=new Child1(); to space optimize. Kiuki esa krne se in future agar mujhe 2nd child ka object banana hai toh p=new Child2(); kr skta hu and puraana vaala Child1 ka object delete ho jaaega coz use koi refer nhi kr rha. But aagar esa nhi krta toh mujhe new vaiable banana padta and puraana vala delete bhi nhi hota.
- **this** keyword is used to refer the current object which called the function. Toh **this** ka use sirf methods mai hoga and static methods mai nhi hoga

### Constructors
1. Constructor call hone par pehle memory allocate hogi then parent class ka constructor call hoga fir khudka constructor chalega.
2. Abstract class and Interface ke dono ke objects nhi hote but still Abstract class ke constructor hote hai kiuki jo class abstract class ko implement kregi uska constructor call hoga toh uska parent abstract class ka bhi call hoga. Interface mai constructor bhi nhi hota.

### Interface
1. Abstract class and Interfaces mai methods ka declaration hota hai, body nhi hoti toh agar method hi ni hai toh object banane ka sense bhi nhi hai isliye un ke paas objects nhi hote.
2. Abstract class and Interface ke dono ke objects nhi hote but still Abstract class ke constructor hote hai kiuki jo class abstract class ko implement kregi uska constructor call hoga toh uska parent abstract class ka bhi call hoga. Interface mai constructor bhi nhi hota.
3. Interface contains abstract and public methods(jisse implementation class un public methods ko override kr ske)
4. All variables in Interface are public(jisse lower class jo interface ko implement kr rhi hai vo usse access kr ske), static(interface ke objects nhi hote), final(ek subclass ne agar variable change kra toh saare sub classes ke liye variable change ho jaaega, isliye esa nhi ho uske like final hote hai. Final vaiables can not be changed and unhe initialse krte time hi value daalni padti hai).
5. Multiple Inheritance is achieved by interfaces only.

### Abstract Class
1. No objects, but still has constructors.

### Object class
Object class is the parent class of all classes in java. It has following methods-: 
1. hashcode()-: unique id for each object
2. toString()-: It convert the details of the object(like its class, its variable values,hashcode) into a string, we should override it
3. equals()-: a==b checks whether a and b points to same object or not, But a.equals(b) check a ki inside values , b ki inside values se same hai ki nhi
4. finalize()-: Garbage collector calls it before destroying the object