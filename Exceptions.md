### Difference between Error and Exception
In Java, both errors and exceptions are types of "throwable" objects that can be used to signal problems *during program execution* means both occur at *Runtime*. However, they are different in terms of their use cases and handling.
1. Errors  
Definition: Errors are serious problems that a reasonable application should not try to catch. They represent problems with the environment in which the application is running, rather than with the code itself.  
Examples: OutOfMemoryError, StackOverflowError, VirtualMachineError.  
Handling: Errors are typically not caught or handled by the application because they are usually beyond the control of the programmer. Instead, they are intended to signal conditions where the application cannot recover.  
Occurrence: Errors usually occur due to resource exhaustion, such as running out of memory, or other critical system-level failures.  
2. Exceptions
Definition: Exceptions are conditions that a program might want to catch and handle. They represent problems that can be anticipated and recovered from, to some extent, by the program.  
Examples: NullPointerException, IOException, SQLException, ArrayIndexOutOfBoundsException.  
Handling: Exceptions can be caught and handled using try, catch, and finally blocks. The program can recover from an exception and continue execution.  

### Checked and Unchecked Exceptions
1. Checked Exceptions: Definition: Checked exceptions are exceptions that are checked at compile-time. The Java compiler forces the programmer to handle these exceptions either by using a try-catch block or by declaring the exception in the method signature using the throws keyword.Like jaise jab apan JDBC/File Handling ke operations krte hai toh bina program run kre hi error aa ajaata hai ki us jo bhi opertion kr rhe ho unko handle kro, else vo compile hi nhi hoga. Ye pehele se compiler force krta hai apan ko handle krne ke liye ki taaki jo bhi potential issues hai jaise data loss, corruption hai usse bach sake     
#### Without Checked Exceptions: If the IOException was not a checked exception, a programmer might forget to handle this scenario, leading to potential crashes if the file is missing or inaccessible.
#### With Checked Exceptions: The compiler forces you to either handle the IOException with a try-catch block or declare it with throws IOException, ensuring that you acknowledge and manage this possible issue.
2. Unchecked Exceptions: Also known as runtime exceptions, these do not need to be declared or caught. These exceptions are typically the result of programming errors, such as NullPointerException,ArrayIndexOutOfBoundsException,ArithmeticException,IllegalArgumentException and occur at runtime without prior compile-time checks. Ye voh Exceptions hai jo compiler pehle se handle krne ko ni bolta, jaise index out of bounds. Compiler sochta hai ki itna toh dimaag hai user mai ki 5 size ke array mai 6th index ko access nahi karega.But checked vaale mai dimaag ki cheej nhi , aur cheej aati hai jinka dimaag se lena dena nhi balki expected errors se hota hai like agar file present hi nhi hui toh usk access kese kre toh ye pehle se pata hai ki error aa skta hai toh pehle se hi compile time pr handle krlo. Lekin use pehle se ye nhi pata ki programmer mai dimaag nhi hai isliye voh unchecked vaalo ko handle krne ki nhi bolta.
3. Important thing is, Exceptions runtime pr hi aati hai. Unchecked Exceptions toh sahi mai runtime pr hi aati hai, but Checked Exceptions ko jabtak handle nhi kro tab tak program compile hi nhi hoga and agar handle krli toh Checked Exceptions aaegi hi nhi Runtime par kiuki already compile time pr handle krli. But agar nhi kri handle toh compile time error aaegi. Toh Unhandled Checked Exceptions give compile time error and Unchecked exceptions give runtime error.

### Why do we need to handle exception
1. Graceful Error Recovery  
Problem: Without exception handling, any unexpected issue (like file not found, network disconnection, invalid user input) could cause your program to terminate abruptly.  
Solution: Exception handling allows your program to "catch" errors when they occur and respond appropriately, rather than crashing. This can involve retrying the operation, providing a default value, or notifying the user of the problem.  
Example: If a file that your program needs is not found, you can catch the FileNotFoundException and prompt the user to provide the correct file path.
2. Program Stability  
   Problem: Unhandled exceptions can lead to program crashes, which are frustrating for users and can lead to loss of data or unsaved work.  
   Solution: By handling exceptions, you can ensure that your program remains stable and continues to operate even when something goes wrong. This is especially important in long-running or critical systems.   
   Example: A web server might catch exceptions from individual requests to ensure that one failing request doesn’t bring down the entire server.  

### Concepts
- Finally, block will always run whether an exception occurs or not.
- In this case the output of the program will be "Some Mathematical Error occurred", "End of Program". So even after exception, it is executing remaining code.
```java
public class Main2 {
    public static void main(String[] args) {
        try {
            int a = 5;
            int b = 0;
            System.out.println(a / b);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Index is more than or equal to length");
        } catch (ArithmeticException e) {
            System.out.println("Some Mathematical Error occurred");
        } catch (Exception e) {
            System.out.println("Error");
        } 
        System.out.println("End of Program");
    }
}
```


### Keywords
1. try-:contains set of statement where exception can occur
2. catch-:Used to perform specific task if specific exception occurred, like telling the user etc.
3. throw-:It is used to explicitly throw a User defined/ Normal exception
4. finally-: Executes after catch block. Ye hamesha chalega, bhale hi exception aaye ya na aaye. You can close the resources and perform cleanup tasks here.
5. throws-:The throws keyword is used in a method signature to indicate that the method might throw one or more exceptions. When a method declares that it "throws" an exception, it is informing the caller that they must handle the potential exception, either by catching it using a try-catch block or by declaring the exception in their own method signature.

### final vs finally vs finalize
1. keyword used for variable, method,class
2. finally used in exception handling
3. finalize is the function called by Garbage collector before deleting object

### Creating Custom Exception
In Java, you can create your own custom exceptions (user-defined exceptions) by extending the Exception class (for checked exceptions) or the RuntimeException class (for unchecked exceptions). This allows you to create exceptions that are specific to the needs of your application.

Steps to Create a User-Defined Exception
- Define the Exception Class:

1. Create a new class that extends Exception or RuntimeException.
2. Provide constructors in your class to initialize the exception with a custom message or cause.
- Throw the Custom Exception:

You can throw your custom exception using the throw keyword when a specific condition arises in your code.
- Catch and Handle the Custom Exception:

Use try-catch blocks to catch and handle your custom exception.  

Example: Creating a User-Defined Checked Exception  
```java
// Step 1: Define the Custom Exception
public class InsufficientFundsException extends Exception {
public InsufficientFundsException(String message) {
super(message);
}
}

// Step 2: Use the Custom Exception in Code
public class BankAccount {
private double balance;

    public BankAccount(double balance) {
        this.balance = balance;
    }

    public void withdraw(double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Insufficient funds for withdrawal");
        }
        balance -= amount;
    }

    public double getBalance() {
        return balance;
    }
}

// Step 3: Handle the Custom Exception
public class Main {
public static void main(String[] args) {
BankAccount account = new BankAccount(1000);

        try {
            account.withdraw(1500);
        } catch (InsufficientFundsException e) {
            System.out.println("Exception caught: " + e.getMessage());
        }
    }
}
```

Example: Creating a User-Defined Unchecked Exception
```java
// Step 1: Define the Custom Exception
public class InvalidAgeException extends RuntimeException {
public InvalidAgeException(String message) {
super(message);
}
}

// Step 2: Use the Custom Exception in Code
public class Registration {
public void registerUser(int age) {
if (age < 18) {
throw new InvalidAgeException("User must be 18 or older to register");
}
// Registration logic
}
}

// Step 3: Handle the Custom Exception
public class Main {
public static void main(String[] args) {
Registration registration = new Registration();

        try {
            registration.registerUser(16);
        } catch (InvalidAgeException e) {
            System.out.println("Exception caught: " + e.getMessage());
        }
    }
}
```