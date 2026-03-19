# Object Oriented Programming with Java

## Unit – 2 SYLLABUS

Exception Handling: The Idea behind Exception, Exceptions & Errors, Types of Exception, Control Flow in Exceptions, JVM Reaction to Exceptions, Use of try, catch, finally, throw, throws in Exception Handling, In-built and User Defined Exceptions, Checked and Un-Checked Exceptions.
Input /Output Basics: Byte Streams and Character Streams, Reading and Writing File in Java.
Multithreading: Thread, Thread Life Cycle, Creating Threads, Thread Priorities,
Synchronizing Threads, Inter-thread Communication.

## What is Exception and Why it requires?

- Exception handling in Java is a mechanism used to manage and respond to errors that occur  
during the execution of a program.  
- In Java, an exception is an event that occurs during the execution of a program that disrupts  
the normal flow of instructions.
- These exceptions can occur for various reasons, such as invalid input, hardware failure, or  
logical errors in the program.

Exception handling is essential in Java for several reasons:

1. Robustness: Exception handling helps in writing robust code that can gracefully handle errors
  and recover from unexpected situations. Without proper exception handling, a program might
   crash or behave unpredictably when encountering errors.
2. Debugging: Exception handling aids in debugging by providing detailed information about the
  cause of errors when they occur. This information, often in the form of a stack trace, helps
   developers identify the source of the problem and fix it efficiently.
3. Maintainability: By handling exceptions effectively, developers can separate error-handling
  logic from the main program logic. This improves code maintainability by making it easier to
   understand and modify.
4. Graceful Error Reporting: Exception handling allows developers to provide meaningful
  error messages to users, guiding them on how to resolve the issue or take appropriate action.

NOTE: In Java, exception handling is done using try, catch, and finally blocks:

- A `try` block contains the code that may throw an exception.
- A `catch` block catches and handles the exception thrown by the try block.
- A `finally` block contains code that will be executed whether an exception is thrown or
not. It's often used for cleanup tasks like closing resources.

Here's a basic example of exception handling in Java:

```java
try {
	// Code that may throw an exception
	int result = 10 / 0; // This will throw an ArithmeticException
} catch (ArithmeticException e) {
	// Handling the exception
	System.out.println("An arithmetic exception occurred: " + e.getMessage());
} finally {
	// Code that will be executed regardless of whether an exception is thrown
	System.out.println("Finally block executed.");
}
```

In this example, if an ArithmeticException occurs (division by zero), it will be caught by the catch
block, which prints an error message. The finally block will be executed regardless of whether an
exception occurred.

### Difference between Exception and Error

In Java, both exceptions and errors are subclasses of the `Throwable` class, but they serve
different purposes and are used in different contexts:

1. Exceptions:
  - Exceptions represent abnormal conditions that occur during the execution of a program,  
   but from which the program can potentially recover.
  - Exceptions are further divided into two types: checked exceptions and unchecked  
   exceptions.
  - Checked exceptions: These are exceptions that must be either caught or declared to be  
   thrown by the method in which they can occur. Examples include `IOException`,  
   `SQLException`, etc.
  - Unchecked exceptions: Also known as runtime exceptions, these exceptions do not need  
   to be explicitly handled or declared. Examples include `NullPointerException`,  
   `ArrayIndexOutOfBoundsException`, etc.
  -  Exceptions are typically caused by external factors such as invalid user input, network  
   issues, or insufficient system resources.
2. Errors:
  - Errors represent abnormal conditions that are beyond the control of the application and  
   usually indicate serious problems that should not be caught or recovered from.
  -  Errors are typically caused by problems external to the application or by internal failures that render the application unable to continue executing.
  -  Examples of errors include `OutOfMemoryError`, `StackOverflowError`,
   `AssertionError`, etc. 
  - Errors are considered fatal and generally cannot be recovered from by the  
   application. They usually signify severe issues that require intervention at the system  
   level.

### Control Flow in Exceptions, JVM Reaction to Exceptions, Use of

### try, catch, finally, throw, throws in Exception Handling

In Java, exception handling allows you to manage unexpected or exceptional situations that may
occur during the execution of a program. Let's delve into each aspect you mentioned:
Control Flow in Exceptions:
 When an exception occurs in Java, the normal flow of control is disrupted.
 The exception is thrown, and the Java runtime system searches for an appropriate exception
handler to process it. If a suitable handler is found, the control flow is transferred to the
catch block associated with that handler.
 If no appropriate handler is found in the current method, the method terminates, and the
control is passed to the calling method, continuing this search up the call stack until a
suitable handler is found or until the exception reaches the top level of the program,
resulting in termination of the program.

JVM Reaction to Exceptions:
 When an exception occurs, the Java Virtual Machine (JVM) reacts by creating an object
known as an "exception object" to represent the exception.
 This object contains information about the type of exception, the location where the
exception occurred, and other relevant details.
 The JVM then looks for an appropriate exception handler to process the exception.
 If a handler is found, the control flow is transferred to the corresponding catch block.
 If no handler is found, the JVM terminates the execution of the program and prints a stack
trace, which provides information about the sequence of method calls that led to the
exception.

Use of try, catch, finally, throw, throws in Exception Handling:

```
 try: The `try` block encloses the code that may potentially throw an exception. It is
followed by one or more catch blocks or a finally block, or both.
 catch: A `catch` block catches and handles exceptions that are thrown within the
corresponding try block. It specifies the type of exception it can catch and contains code to
handle the exception.
 finally: The `finally` block contains code that is executed regardless of whether an
exception is thrown or not. It is often used to release resources, such as closing files or
database connections.
 throw: The `throw` keyword is used to explicitly throw an exception within a method or
block of code. It is typically followed by an instance of an exception class or subclass.
 throws: The `throws` keyword is used in method declarations to indicate that the method
may throw certain types of exceptions. It specifies the exceptions that the method can
throw, allowing the caller of the method to handle those exceptions or propagate them
further.
```

Here's a basic example demonstrating the use of these keywords:

```java
try {
	// Code that may throw an exception
	if (condition) {
	throw new SomeException("Something went wrong.");
	}
} catch (SomeException e) {
	// Handling the exception
	System.out.println("An exception occurred: " + e.getMessage());


} finally {
	// Code that will be executed regardless of whether an exception is thrown
	System.out.println("Finally block executed.");
}
```

In this example, if the condition is true, a `SomeException` is explicitly thrown using the `throw`
keyword. The catch block catches and handles this exception, and the finally block is executed
regardless of whether an exception occurred.

### User Define and Predefine Exceptions

In Java, exceptions can be categorized into two main types: built-in (inbuilt) exceptions provided
by the Java API, and user-defined exceptions created by developers according to specific
application requirements.

Built-in Exceptions:
Java provides a set of built-in exceptions in the `java.lang` package to handle common error
conditions. These exceptions are part of the Java API and cover a wide range of error scenarios.
Some common built-in exceptions include:

```
 `NullPointerException`: Thrown when attempting to access or invoke a method on an
object reference that is `null`.
 `ArithmeticException`: Thrown when an arithmetic operation (such as division by zero)
is attempted.
 `ArrayIndexOutOfBoundsException`: Thrown when attempting to access an array
element at an invalid index.
 `IOException`: Base class for exceptions related to input/output operations.
```

```
 `NumberFormatException`: Thrown when a method that parses a string to a numeric
type encounters an invalid format.
 `ClassNotFoundException`: Thrown when a class loader cannot find the class specified
by its name.
```

User-defined Exceptions:

```
 Sometimes, the built-in exceptions provided by Java may not fully capture the specific
error conditions of an application.
 In such cases, developers can create their own custom exceptions by extending the
`Exception` class or one of its subclasses.
 User-defined exceptions allow developers to define their own exception types with custom
error messages and additional information specific to their application domain.
```

Here's an example of a user-defined exception:

```java
// Custom exception class
class MyCustomException extends Exception {
	public MyCustomException(String message) {
	super(message);
	}
}

// Example usage
class MyClass {
	public void someMethod() throws MyCustomException {
	// Some condition that warrants throwing the custom exception
		if (condition) {


		throw new MyCustomException("Custom error message");
		}
	}
}
```

In this example, `MyCustomException` is a user-defined exception class that extends the
`Exception` class. The `someMethod()` throws this custom exception if a certain condition is
met.

User-defined exceptions are particularly useful for encapsulating application-specific error
conditions and providing clear and meaningful error messages to users or developers.

In summary, while built-in exceptions cover common error conditions, user-defined exceptions
allow developers to create custom exception types tailored to the specific requirements of their
applications.

### Difference between Checked and Un-Checked Exceptions

Checked and unchecked exceptions are two categories of exceptions in Java, distinguished
primarily by how the compiler enforces handling or declaration of these exceptions.

Checked Exceptions:

Enforced Handling or Declaration:

- Checked exceptions are checked at compile-time by the compiler. This means that the
compiler ensures that code either handles the checked exception using a `try-catch` block or
declares that it might throw the exception using the `throws` clause in the method signature.

Subclass of Exception:

- Checked exceptions are subclasses of the `Exception` class (excluding `RuntimeException`
and its subclasses).
Examples:
- Common examples of checked exceptions include `IOException`, `SQLException`,
`FileNotFoundException`, etc.
Common Use Cases:
- Checked exceptions are typically used for conditions that can reasonably be expected to occur
during normal execution of a program and that a programmer should be able to anticipate and
recover from, such as file I/O errors, network errors, database errors, etc.

Unchecked Exceptions:

Not Enforced Handling or Declaration:

- Unchecked exceptions are not checked at compile-time by the compiler. This means that the
compiler does not enforce handling or declaration of unchecked exceptions.

Subclass of Runtime Exception:

- Unchecked exceptions are subclasses of the `RuntimeException` class (or its subclasses).
Examples:
- Common examples of unchecked exceptions include `NullPointerException`,
`ArrayIndexOutOfBoundsException`, `ArithmeticException`, `IllegalArgumentException`, etc.
Common Use Cases:
- Unchecked exceptions are typically used for programming errors or conditions that are outside
the programmer's control and that cannot be reasonably anticipated or recovered from, such as
null pointer dereference, array index out of bounds, arithmetic errors, etc.

Key Differences:

```
 Enforcement: Checked exceptions are enforced by the compiler, whereas unchecked
exceptions are not.
 Handling or Declaration: Checked exceptions must be handled or declared using `try-
catch` blocks or the `throws` clause, while unchecked exceptions do not have this
requirement.
 Inheritance: Checked exceptions inherit from the `Exception` class, while unchecked
exceptions inherit from the `RuntimeException` class.
 Use Cases: Checked exceptions are typically used for recoverable conditions, while
unchecked exceptions are used for unrecoverable conditions or programming errors.
```

### Input and Output in Java

In Java, streams are a fundamental abstraction for handling input and output (I/O) operations.
Streams provide a consistent way to read from or write to different data sources, such as files,
network connections, or memory buffers. Java's I/O API includes two main types of streams: byte
streams and character streams.
Byte Streams:

```
 Byte streams operate directly with raw binary data, reading and writing data in the form of
bytes. They are used for input and output of raw binary data, such as images, audio files,
or binary data in general.
 Byte streams are typically represented by classes whose names end with `InputStream` or
`OutputStream`. Some common byte stream classes include:
```

- `InputStream`: Base class for byte input streams.
- `OutputStream`: Base class for byte output streams.
- `FileInputStream`: Reads data from a file as a sequence of bytes.
- `FileOutputStream`: Writes data to a file as a sequence of bytes.
- `ByteArrayInputStream`: Reads data from a byte array.
- `ByteArrayOutputStream`: Writes data to a byte array.

Here's a simple example of reading from a file using byte streams:

```java
try (FileInputStream fis = new FileInputStream("example.txt")) {
	int byteRead;
	while ((byteRead = fis.read()) != -1) {
	System.out.print((char) byteRead); // Convert byte to char and print
}


} catch (IOException e) {
		e.printStackTrace();
}
```

Character Streams:

```
 Character streams, on the other hand, handle Unicode characters instead of raw bytes. They
are used for input and output of text data, providing support for character encoding and
decoding. Character streams are typically represented by classes whose names end with
`Reader` or `Writer`. Some common character stream classes include:
```

- `Reader`: Base class for character input streams.
- `Writer`: Base class for character output streams.
- `FileReader`: Reads text data from a file using the platform's default character encoding.
- `FileWriter`: Writes text data to a file using the platform's default character encoding.
- `BufferedReader`: Reads text from a character-input stream, buffering characters to provide
efficient reading of characters, arrays, and lines.
- `BufferedWriter`: Writes text to a character-output stream, buffering characters to provide
efficient writing of characters, arrays, and strings.

Here's an example of reading from a file using character streams:

```java
try (FileReader fr = new FileReader("example.txt");
BufferedReader br = new BufferedReader(fr)) {
	String line;
	while ((line = br.readLine()) != null) {
		System.out.println(line);
	}
} catch (IOException e) {
	e.printStackTrace();
}
```

### Reading Files in Java

Reading files in Java involves using the input stream classes provided by the Java I/O API. Here's
a basic example of how you can read a text file in Java:

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class ReadFileExample {
	public static void main(String[] args) {
	String filename = "example.txt";

	try (BufferedReader reader = new BufferedReader(new FileReader(filename))) {
		String line;
		while ((line = reader.readLine()) != null) {
			System.out.println(line);
		}
	} catch (IOException e) {
	e.printStackTrace();
	}


}
}
```

In this example:

 We import necessary classes from the `java.io` package.
 We specify the name of the file we want to read (`example.txt`).
 Inside the `try` block, we create a `BufferedReader` object wrapped around a `FileReader`
object. The `BufferedReader` provides efficient reading of characters, arrays, and lines
from the input stream.
 We use a `while` loop to read each line of the file until the end of the file is reached
(`readLine()` returns `null`).
 Inside the loop, we print each line to the console.
 The `try`-with-resources statement is used to ensure that the `BufferedReader` is properly
closed after reading the file, even if an exception occurs.
 If an `IOException` occurs during file reading, we print the stack trace.
Make sure to replace `"example.txt"` with the path to your actual file.

### Writing Files in Java

 Writing files in Java involves using the output stream classes provided by the Java I/O API.
Here's a basic example of how you can write text to a file in Java:

```java
import java.io.BufferedWriter;
import java.io.FileWriter;
import java.io.IOException;


public class WriteFileExample {
    public static void main(String[] args) {
        String filename = "output.txt";

        try (BufferedWriter writer = new BufferedWriter(new FileWriter(filename))) {
            writer.write("Hello, World!");
            writer.newLine(); // Add a new line
            writer.write("This is a test file.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

In this example:

 We import necessary classes from the `java.io` package.
 We specify the name of the file we want to write to (`output.txt`).
 Inside the `try` block, we create a `BufferedWriter` object wrapped around a `FileWriter`
object. The `BufferedWriter` provides efficient writing of characters, arrays, and strings to
the output stream.
 We use the `write()` method to write the desired content to the file. We also use `newLine()`
method to add a new line after writing the first line.
 The `try`-with-resources statement is used to ensure that the `BufferedWriter` is properly
closed after writing to the file, even if an exception occurs. 4 If an `IOException` occurs
during file writing, we print the stack trace.

Make sure to replace `"output.txt"` with the path to your desired file.

### What is Multithreading

 Multithreading in Java refers to the capability of a Java program to execute multiple threads
concurrently.
 A thread is a lightweight process, and multithreading allows multiple threads to exist within
the context of a single process.
 This enables a Java program to perform multiple tasks simultaneously, improving
performance and responsiveness.

Here are some key concepts related to multithreading in Java:

1. Thread: A thread is the smallest unit of execution within a process. Java programs can create
  and manage threads using the `Thread` class or by implementing the `Runnable` interface.
2. Thread States: Threads can be in different states during their lifecycle, including `NEW`,
  `RUNNABLE`, `BLOCKED`, `WAITING`, `TIMED_WAITING`, and `TERMINATED`.
3. Thread Lifecycle: The lifecycle of a thread includes creation, starting, running, blocking,
  waiting, timing waiting, and termination. Threads can transition between these states based on
   their execution and interactions with other threads.
4. Thread Synchronization: When multiple threads access shared resources concurrently, it can
  lead to synchronization issues such as race conditions and data inconsistency. Java provides
   synchronization mechanisms like `synchronized` blocks and methods, `volatile` keyword, and
   explicit locks (e.g., `ReentrantLock`) to ensure thread-safe access to shared resources.
5. Concurrency Utilities: Java provides a rich set of concurrency utilities in the
  `java.util.concurrent` package. These utilities include thread pools, concurrent collections (e.g.,
   `ConcurrentHashMap`, `ConcurrentLinkedQueue`), atomic variables (e.g., `AtomicInteger`,
   `AtomicLong`), and higher-level concurrency constructs like `Executor`, `ExecutorService`, and
   `Future`.
6. Thread Priorities: Threads can have priorities ranging from 1 to 10, where 1 is the lowest
  priority and 10 is the highest. However, thread priorities are platform-dependent and may not
   have a significant impact on thread scheduling.
7. Thread Groups: Thread groups provide a way to manage and organize threads into
  hierarchical groups. However, thread groups are considered obsolete and are not commonly used
   in modern Java applications.

### Differences b/w Process and Thread

Threads and processes are both fundamental concepts in operating systems and concurrent
programming, but they represent different units of execution with distinct characteristics. Here
are the key differences between threads and processes:

1. Definition:

- Thread: A thread is the smallest unit of execution within a process. Threads share the same
memory space and resources within the process and can execute concurrently with other threads.
- Process: A process is an independent program unit that runs in its own isolated memory space.
Each process has its own address space, resources, and execution environment.

1. Resource Allocation:

- Thread: Threads within the same process share resources such as memory, file handles, and
other process-wide resources. Threads can communicate and synchronize with each other
efficiently.
- Process: Processes are independent entities with separate memory spaces and resources.
Processes do not share memory or resources by default and communicate through inter-process
communication (IPC) mechanisms.

1. Communication and Synchronization:

- Thread: Threads within the same process can communicate directly and share data through
shared memory. Synchronization mechanisms like locks, semaphores, and monitors can be used
to coordinate access to shared resources.
- Process: Processes communicate and synchronize using IPC mechanisms such as pipes,
sockets, message queues, and shared memory segments. These mechanisms incur higher
overhead compared to thread communication within the same process.

1. Creation Overhead:

- Thread: Creating a thread is relatively lightweight compared to creating a new process.
Threads share the same address space and resources with the parent process, so creating a new
thread involves minimal overhead.
- Process: Creating a new process is more resource-intensive compared to creating a thread.
Each process has its own address space and requires the allocation of separate resources by the
operating system.

1. Isolation and Fault Tolerance:

- Thread: Threads within the same process are not isolated from each other. If one thread
crashes due to an unhandled exception, it can potentially affect the entire process and cause it to
crash.
- Process: Processes are isolated from each other, and failures in one process typically do not
affect other processes. Operating systems provide process isolation and fault tolerance to ensure
stability and reliability.

### Creating Threads in Java with Life Cycle

The lifecycle of a thread in Java consists of several states that a thread transitions through from
its creation to its termination. Here's a breakdown of the thread lifecycle stages:

1. New: When a thread is created, it is in the "new" state. In this state, the thread has been
  instantiated, but the `start()` method hasn't been called yet to start the execution of the thread.
2. Runnable: After calling the `start()` method on a thread object, it enters the "runnable" state.
  In this state, the thread is ready to run, but the scheduler has not yet selected it to be the running
   thread.
3. Running: Once the scheduler selects a thread from the runnable pool, the thread enters the
  "running" state. In this state, the thread's `run()` method is being executed.
4. Blocked/Waiting: A running thread might transition to the "blocked" or "waiting" state under
  certain conditions. For example, if it's waiting for I/O operations to complete or for a lock to be
   released. In these states, the thread is not executing, but it's not ready to run either.
5. Timed Waiting: Similar to the "waiting" state, but with a specified timeout period. Threads
  can enter this state when they call methods like `sleep()` or `wait()` with a timeout parameter.
6. Terminated: A thread enters the "terminated" state when its `run()` method completes or when
  an uncaught exception terminates the thread.

Here's an example demonstrating thread creation and the lifecycle stages in Java:

```java
class MyThread extends Thread {
@Override
public void run() {
System.out.println("Thread is running.");
try {
Thread.sleep(2000); // Simulate some work


} catch (InterruptedException e) {
e.printStackTrace();
}
System.out.println("Thread is terminating.");
}
}
public class ThreadLifecycleExample {
public static void main(String[] args) {
// Create a new thread
MyThread thread = new MyThread();
// Start the thread
thread.start();

// At this point, the thread is in the "runnable" state

// Perform some other tasks while the thread is running

// Wait for the thread to finish
try {
thread.join(); // Wait for the thread to terminate
} catch (InterruptedException e) {
e.printStackTrace();
}

// At this point, the thread has terminated
System.out.println("Main thread exiting.");
}
}
```

In this example:
 We create a custom thread by extending the `Thread` class and overriding the `run()`
method.We create an instance of our custom thread (`MyThread`) and call its `start()`
method to start its execution. The thread transitions to the "runnable" state.
 While the thread is running, we can perform other tasks in the main thread. We use the
`join()` method to wait for the custom thread to finish its execution. The main thread waits
until the custom thread terminates.
 Once the custom thread terminates, the main thread continues its execution.

### Threads Synchronization in Java

 Thread synchronization in Java is the process of coordinating the execution of multiple
threads to ensure that they access shared resources in a safe and orderly manner.
 Without proper synchronization, concurrent access to shared resources may lead to data
corruption, race conditions, and other concurrency-related bugs.

Java provides several mechanisms for thread synchronization:

1. Synchronized Blocks:

- Synchronized blocks allow you to specify a block of code that can be executed by only one
thread at a time. This ensures that multiple threads do not execute the synchronized code
simultaneously.
- Synchronization is achieved by using the `synchronized` keyword followed by an object
reference or class literal.
- Example:

```java
synchronized (sharedObject) {
// Synchronized code block
}
```

1. Synchronized Methods:

- You can also synchronize entire methods by using the `synchronized` keyword in the method
declaration. This ensures that only one thread can execute the synchronized method at a time.
- Example:

```java
public synchronized void synchronizedMethod() {
// Synchronized method
}
```

1. Reentrant Locks:

- The `java.util.concurrent.locks.ReentrantLock` class provides a flexible alternative to
synchronized blocks and methods. It allows finer-grained control over locking and unlocking and
supports advanced features such as deadlock detection, timeout, and condition variables.
- Example:

```java
ReentrantLock lock = new ReentrantLock();
lock.lock();
try {
// Synchronized code block
} finally {
lock.unlock();
}
```

1. Volatile Keyword:

- The `volatile` keyword is used to declare variables that are accessed by multiple threads. It ensures that changes
to the variable made by one thread are visible to other threads immediately.
- Example:

```java
private volatile boolean flag;
```

1. Atomic Classes:

- Java provides atomic classes in the `java.util.concurrent.atomic` package, such as
`AtomicInteger`, `AtomicLong`, etc. These classes provide atomic operations on primitive types
and eliminate the need for explicit synchronization.
- Example:

```java
AtomicInteger count = new AtomicInteger(0);
count.incrementAndGet();
```

Thread synchronization is essential for ensuring the correctness and consistency of concurrent
programs. It helps prevent race conditions, data corruption, and other concurrency-related issues
by ensuring that shared resources are accessed in a mutually exclusive manner.

# Thank You!

