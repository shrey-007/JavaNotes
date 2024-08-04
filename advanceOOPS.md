### final keyword
1. If used with PDT toh uski value change nhi ho skti
2. If used with object toh , us object ki properties change ho skti hai but uska reference variable change nhi hoga
3. If used in method toh method ko override nhi kr skte
4. If used in class, then it can not be extended

### static keyword
1. Something which is not dependent on object. Methods and variables both can be static
2. Static variable vo hai jo particular object ki property nhi balki poori class ki property hai, so it is accessed by class name ClassName.variable.
3. **Non static method can be referenced from a static context** is an error when you call non-static method(jise object chaiye) from a static method(jo bina object ke chala)
4. ```java
    public static void staticFunc1(){
        staticFunc2(); // can call static function inside a static function, both of them don't require object
        func1();       // this will give error, because staticFunc1() ko kisi object ne call nhi kiya toh iske paas koi object nhihai and func1() ko object chaiye run krne ke liye toh vo aaega kaha se.
        // however if you create a object here itself then call, then it will not give error-:
        Main main=new Main();
        main.func1();  // this will not give error
    }
    public static void staticFunc2(){

    }
    public void func1(){
        func2();      // can call non-static function inside non-static function, Jis object ne func1() ko call kra vahi object func2() ko call kr dega
        staticFunc2(); // can also call static function inside non-static function.
    }
    public void func2(){
        
    }
   ```
5. static methos ke under **this** keyword use nhi kr skte, coz **this** refers to the object jisne call kra, and static method ko kisi object ne call nhi kara.



### this and super
1. Both are used inside non-static methods only
2. this is used to refer to current object and ab us current object se kuch bhi kr skte hai , constructor call , method call, access variable
```java
func(){
    this(a);  // constructor
    this.func2();  // method
    this.color=red;  // property
}
```
3. super is used to access members of parent class
```java
func(){
        super(a);  // constructor of super class
        super.func2();  // method of super class
        super.color=red;  // property of super class
        }
```
