
---

Q.1 What is a package? Write down all the steps for package creation with an example.

What is a Package?
A package in Java is a mechanism for organizing related classes and interfaces into a single namespace. It is like a folder in a file system. Packages are used to:

· Avoid naming conflicts: Two classes can have the same name if they are in different packages.
· Provide access protection: Classes within a package can have controlled visibility.
· Make classes easier to locate and use.

Steps for Package Creation:

1. Declare the package: At the very beginning of your Java source file (before any import statements), use the package keyword followed by the name of the package.
   ```java
   package mypackage;
   ```
2. Create the directory structure: The package name must mirror the directory structure. For a package mypackage, the .java file must be inside a folder named mypackage. For a nested package like com.example.myapp, you would need the directory structure com/example/myapp/.
3. Write the Java class: Create your Java class inside the file and save it within the correct package directory.
4. Compile the Java file: To compile, you must be in the directory that contains the package folder. Use the javac command.
   ```bash
   javac mypackage/MyClass.java
   ```
   You can also use the -d option to specify the destination directory for the compiled .class files and let the compiler create the directory structure automatically.
   ```bash
   javac -d . MyClass.java
   ```
   The . (dot) means the current directory.
5. Use the class from another package: To use a class from a package, you must either use its fully qualified name (mypackage.MyClass) or import it using the import keyword.
   ```java
   import mypackage.MyClass;
   // or
   import mypackage.*;
   ```

Example:

Let's create a simple package called mypack with a class MyMessage.

Step 1 & 2: Create a directory named mypack.
Step 3: Inside mypack, create a file MyMessage.java:

```java
// File: mypack/MyMessage.java
package mypack; // Declaring the package

public class MyMessage {
    public String getMessage() {
        return "Hello from the mypack package!";
    }
}
```

Step 4: Compile from the parent directory of mypack:

```bash
javac mypack/MyMessage.java
```

Step 5: Now, create another Java file in the parent directory to use this package:

```java
// File: TestPackage.java
import mypack.MyMessage; // Importing the class from the package

public class TestPackage {
    public static void main(String[] args) {
        MyMessage msg = new MyMessage(); // Using the imported class
        System.out.println(msg.getMessage());
    }
}
```

Step 6: Compile and run TestPackage:

```bash
javac TestPackage.java
java TestPackage
```

Output:

```
Hello from the mypack package!
```

---

Q.2 Define an exception. What are the key terms used in exception handling? Explain.

What is an Exception?
An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions. It is an unwanted or unexpected event that arises at runtime, such as dividing by zero, accessing an array with an invalid index, or trying to open a file that doesn't exist.

Key Terms in Exception Handling:

1. try: The try keyword is used to define a block of code that may cause an exception. This block of "risky" code is monitored for exceptions. A try block must be followed by at least one catch or finally block.
   ```java
   try {
       // Code that might throw an exception
   }
   ```
2. catch: The catch keyword is used to handle a specific type of exception. It is declared immediately after a try block. When an exception is thrown in the try block, the program looks for a matching catch block to handle it.
   ```java
   catch (ExceptionType e) {
       // Code to handle the exception
   }
   ```
3. finally: The finally keyword is used to create a block of code that always executes after the try-catch structure, regardless of whether an exception was thrown or caught. It is typically used for cleanup activities, like closing files or database connections.
   ```java
   finally {
       // Cleanup code, always executed
   }
   ```
4. throw: The throw keyword is used to explicitly throw an exception. You can throw a built-in exception or a custom exception that you have created.
   ```java
   if (age < 18) {
       throw new ArithmeticException("Not a valid age.");
   }
   ```
5. throws: The throws keyword is used in a method signature to declare that the method might throw one or more exceptions. It informs the caller of the method about the potential exceptions, so the caller can handle them.
   ```java
   public void readFile(String path) throws IOException {
       // Method code that might throw an IOException
   }
   ```

---

Q.3

(i) How do you create your own exception class? Explain with a program.

To create your own exception class (a custom or user-defined exception), you need to extend the Exception class (to make it a checked exception) or RuntimeException (to make it an unchecked exception). It's common practice to create a constructor that accepts a String message and passes it to the superclass.

Program Example:

```java
// Custom exception class (Checked Exception)
class InvalidAgeException extends Exception {
    public InvalidAgeException(String message) {
        super(message); // Pass the message to the parent Exception class
    }
}

public class CustomExceptionDemo {

    // Method that declares it might throw the custom exception
    static void validateAge(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age must be 18 or above."); // Throwing custom exception
        } else {
            System.out.println("Valid age: " + age);
        }
    }

    public static void main(String[] args) {
        try {
            validateAge(16); // This will cause the exception
        } catch (InvalidAgeException e) {
            System.out.println("Caught Exception: " + e.getMessage());
        }
    }
}
```

Output:

```
Caught Exception: Age must be 18 or above.
```

(ii) Demonstrate the working of a nested try block with an example.

A nested try block is a try block inside another try block. This structure is useful when different sections of code might throw different exceptions, and you want to handle them with more granularity. If an exception is thrown in the inner try block and is not caught by its corresponding catch block, it will propagate to the catch blocks of the outer try block.

Example:

```java
public class NestedTryDemo {
    public static void main(String[] args) {
        try { // Outer try block
            int[] numbers = {1, 2, 3};
            int divisor = 0;

            try { // Inner try block 1
                int result = numbers[2] / divisor; // ArithmeticException (division by zero)
                System.out.println("Result: " + result);
            } catch (ArithmeticException e) {
                System.out.println("Inner Catch: Cannot divide by zero.");
            }

            try { // Inner try block 2
                System.out.println("Value at index 5: " + numbers[5]); // ArrayIndexOutOfBoundsException
            } catch (ArrayIndexOutOfBoundsException e) {
                System.out.println("Inner Catch: Array index is out of bounds.");
            }

            System.out.println("End of nested try operations.");

        } catch (Exception e) { // Outer catch block
            System.out.println("Outer Catch: An unexpected error occurred.");
        }
    }
}
```

Output:

```
Inner Catch: Cannot divide by zero.
Inner Catch: Array index is out of bounds.
End of nested try operations.
```

(iii) Checked & unchecked exceptions: Write a Java program to demonstrate arithmetic exception handling.

· Checked Exceptions: These are exceptions that are checked at compile-time. The compiler forces the programmer to handle them (e.g., IOException, ClassNotFoundException).
· Unchecked Exceptions: These are exceptions that occur at runtime. They are not checked at compile-time, so the programmer is not forced to handle them (e.g., ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException).

The following program demonstrates handling an unchecked ArithmeticException.

Program Example:

```java
import java.util.Scanner;

public class ArithmeticExceptionDemo {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter numerator: ");
        int num = scanner.nextInt();
        System.out.print("Enter denominator: ");
        int den = scanner.nextInt();

        try {
            // This line might throw an ArithmeticException if den is 0
            int result = num / den;
            System.out.println("Result: " + result);
        }
        catch (ArithmeticException e) {
            // Handling the unchecked exception
            System.out.println("Error: Cannot divide by zero. " + e);
        }
        finally {
            System.out.println("This is the finally block, always executed.");
            scanner.close();
        }
    }
}
```

Sample Output (if denominator is 0):

```
Enter numerator: 10
Enter denominator: 0
Error: Cannot divide by zero. java.lang.ArithmeticException: / by zero
This is the finally block, always executed.
```

---

Q.4 Differentiate between character streams and byte streams. Write a Java program for reading a character from a file and write a character in the file.

Difference between Character Streams and Byte Streams:

Feature Byte Streams Character Streams
Data Handling Handles I/O of raw binary data (bytes). Handles I/O of characters, automatically handling Unicode.
Base Classes InputStream (read) and OutputStream (write). Reader (read) and Writer (write).
Common Classes FileInputStream, FileOutputStream, BufferedInputStream. FileReader, FileWriter, BufferedReader, PrintWriter.
Use Case Suitable for all types of data, especially non-text files like images, audio, video, and executable files. Suitable for text files, as they handle character encoding (like UTF-8, UTF-16) conversions.

Java Program for Reading and Writing a Character from/to a File:

This program demonstrates writing a single character to a file and then reading a single character from the same file.

```java
import java.io.FileReader;
import java.io.FileWriter;
import java.io.IOException;

public class CharStreamDemo {
    public static void main(String[] args) {
        String filename = "sample.txt";
        char charToWrite = 'A';

        // 1. Write a character to the file using FileWriter
        try (FileWriter writer = new FileWriter(filename)) {
            writer.write(charToWrite);
            System.out.println("Successfully written character '" + charToWrite + "' to file: " + filename);
        } catch (IOException e) {
            System.out.println("An error occurred during writing.");
            e.printStackTrace();
        }

        // 2. Read a character from the file using FileReader
        try (FileReader reader = new FileReader(filename)) {
            int charData; // FileReader.read() returns an integer representing the character or -1 for EOF

            // Read the first character (or loop to read all)
            charData = reader.read();
            if (charData != -1) {
                char charRead = (char) charData;
                System.out.println("Successfully read character '" + charRead + "' from file: " + filename);
            } else {
                System.out.println("File is empty.");
            }

        } catch (IOException e) {
            System.out.println("An error occurred during reading.");
            e.printStackTrace();
        }
    }
}
```

---

Q.5 Explain the concept of multithreading. Describe the ways to create threads in Java with suitable code. Also explain which method is more suitable to create threads.

Concept of Multithreading:
Multithreading in Java is a process of executing multiple threads simultaneously. A thread is a lightweight sub-process, the smallest unit of processing. It is a separate path of execution within a program. Multithreading allows a program to perform multiple tasks concurrently, maximizing the utilization of the CPU and improving performance, especially in multi-core systems.

Ways to Create Threads in Java:

There are two primary ways to create a thread:

1. By Extending the Thread class:
   · Create a class that extends the java.lang.Thread class.
   · Override the run() method. The code that constitutes the new thread's task goes inside the run() method.
   · Create an instance of your class and call its start() method. The start() method creates a new thread and calls the run() method internally.
   ```java
   // Method 1: Extending Thread class
   class MyThread extends Thread {
       public void run() {
           System.out.println("Thread is running (extending Thread). Name: " + Thread.currentThread().getName());
       }
   }
   
   public class ThreadDemo1 {
       public static void main(String[] args) {
           MyThread thread1 = new MyThread();
           thread1.start(); // Starts the new thread
       }
   }
   ```
2. By Implementing the Runnable interface:
   · Create a class that implements the java.lang.Runnable interface.
   · Implement the run() method.
   · Create an instance of your class and pass it as a parameter to the constructor of the Thread class.
   · Call the start() method on the Thread object.
   ```java
   // Method 2: Implementing Runnable interface
   class MyRunnable implements Runnable {
       public void run() {
           System.out.println("Thread is running (implementing Runnable). Name: " + Thread.currentThread().getName());
       }
   }
   
   public class ThreadDemo2 {
       public static void main(String[] args) {
           MyRunnable myRunnable = new MyRunnable();
           Thread thread2 = new Thread(myRunnable);
           thread2.start(); // Starts the new thread
       }
   }
   ```

Which Method is More Suitable?
Implementing the Runnable interface is generally considered a more suitable and preferred way to create threads. The reasons are:

1. Java doesn't support multiple inheritance: If you extend the Thread class, your class cannot extend any other class. By implementing Runnable, your class is free to extend another class.
2. Separation of task and runner: Runnable separates the task (the code in run()) from the mechanism of running it (the Thread class). This promotes better object-oriented design.
3. Reusability: The same Runnable object can be passed to multiple Thread objects, allowing multiple threads to execute the same task.

---

Q.6

(i) Explain the life cycle of a thread.

A thread in Java can be in one of the following states during its life, as defined in the Thread.State enumeration:

1. New: The thread is created but not yet started. It is in this state after instantiation but before calling the start() method.
2. Runnable: After calling start(), the thread is in the runnable state. In this state, the thread is ready to run and is waiting for its turn to be selected for execution by the thread scheduler.
3. Blocked/Waiting: The thread is alive but is not eligible to run. This happens when it is waiting for a monitor lock (blocked), waiting indefinitely for another thread to perform a particular action (wait()), or waiting for another thread with a specified time (sleep(), wait(timeout)).
4. Terminated (Dead): A thread is in this state when it has completed its run() method or has been stopped. Once terminated, it cannot be started again.

(ii) Differentiate between autoboxing/unboxing & wait() and notify(). Where is the need of synchronization? Explain with example.

This question combines two distinct concepts. Let's break them down.

Difference between Autoboxing/Unboxing and wait()/notify():

Feature Autoboxing & Unboxing wait() & notify()
Category Java Language Feature (related to data types) Inter-Thread Communication Mechanism
Purpose Automatic conversion between primitive types (e.g., int) and their corresponding wrapper classes (e.g., Integer). Used for communication between threads. One thread can wait for a condition, and another can notify it when the condition is met.
Usage Used when adding primitives to collections (ArrayList<Integer>), or when working with APIs that expect objects. Used inside a synchronized block or method to coordinate access to a shared resource.
Example Integer i = 100; (autoboxing: int to Integer)   int j = i; (unboxing: Integer to int) wait() makes a thread release the lock and wait.   notify() wakes up one waiting thread.

Need for Synchronization and Example:

Synchronization is needed when multiple threads try to access and modify a shared resource simultaneously. This can lead to data inconsistency or race conditions. Synchronization ensures that only one thread can access the shared resource at a time.

Example (without synchronization):

```java
class Counter {
    int count = 0;
    void increment() { // This method is NOT synchronized
        count++;
    }
}

public class SyncProblemDemo {
    public static void main(String[] args) throws InterruptedException {
        Counter c = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 1; i <= 1000; i++) c.increment();
        });

        Thread t2 = new Thread(() -> {
            for (int i = 1; i <= 1000; i++) c.increment();
        });

        t1.start();
        t2.start();

        t1.join(); // Wait for t1 to finish
        t2.join(); // Wait for t2 to finish

        // The expected final count is 2000, but it will likely be less
        // due to both threads interfering with each other's operations.
        System.out.println("Final count (without sync): " + c.count);
    }
}
```

To fix this, we can add the synchronized keyword to the increment() method. This ensures that if one thread is executing increment(), all other threads must wait for their turn.

```java
synchronized void increment() {
    count++;
}
// Now the final output will consistently be 2000.
```

---

Q.7 Explain inter-thread communication.

Inter-thread communication is a mechanism that allows synchronized threads to communicate with each other. It is achieved using the following methods of the Object class:

· wait(): Tells the current thread to release the lock and wait until another thread invokes notify() or notifyAll() for the same object.
· notify(): Wakes up a single thread that is waiting on this object's monitor.
· notifyAll(): Wakes up all threads that are waiting on this object's monitor.

These methods can only be called from within a synchronized context (synchronized block or method). If called outside a synchronized context, the program will throw IllegalMonitorStateException.

Why is it needed?
It is needed to solve problems where one thread's work is dependent on another thread's work. For example, in a producer-consumer problem, the consumer thread must wait (wait()) if the buffer is empty, and the producer thread must notify (notify()) the consumer after it has produced an item.

Simple Example (Producer-Consumer concept):
Imagine a shared object Message. One thread sets a message, and another prints it.

```java
class Message {
    private String msg;
    private boolean empty = true;

    // Called by Consumer thread
    public synchronized String read() {
        while (empty) { // If no message, wait for it
            try { wait(); } catch (InterruptedException e) {}
        }
        empty = true;
        notifyAll(); // Notify producer that message is read
        return msg;
    }

    // Called by Producer thread
    public synchronized void write(String message) {
        while (!empty) { // If there is an unread message, wait
            try { wait(); } catch (InterruptedException e) {}
        }
        empty = false;
        this.msg = message;
        notifyAll(); // Notify consumer that a message is available
    }
}
```

In this example, wait() and notifyAll() manage the flow of execution, allowing the producer and consumer to work in harmony.
