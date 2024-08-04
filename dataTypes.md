1. There are two type of variables, primitive and non-primitive(user defined/Objects/reference type)
2. Primitive data type stores value. They are directly stored in stack.
3. Non-primitive data type stores address of the object.Stack mai variable ka reference hoga and vo heap mai point kr rha hoga object ko. Means stack mai varibale hoga and usme jo value hogi vo address hogi heap ki jaha vo object stored hai
4. In java there is only pass by value. Bas farak ye hai ki objects ke reference mai values hoti hi nhi hai object ki, usem value uske address ki hoti hai toh jab function mai objects ko bhejte hai toh address jaata hai and us address mai changes ho jaate hai. So basically krte toh pass by value hi hai, but object ke case mai vo apne aap pass by reference ho jaata hai.
5. Wrapper class is a class whose object wraps or contains PDT
6. Wrapper class is used because-:
### Collection Framework
   Java's collection framework, like ArrayList, HashSet, etc., can only store objects, not primitive data types. To store primitives in collections, you need to convert them to their corresponding wrapper class objects.
### Autoboxing and Unboxing
   Autoboxing is the automatic conversion of a primitive type into its corresponding wrapper class, while Unboxing is the reverse process.
   This feature makes it easier to work with primitives in situations where objects are required, as the conversion is handled automatically.
### Utility Methods
   Wrapper classes provide several utility methods for converting between types, parsing strings into primitives, and other useful operations. For example, Integer.parseInt() converts a string to an integer.
### Null Values
   Primitive data types cannot hold a null value, but their wrapper class counterparts can. This is useful in scenarios like database operations where a field may be null.

