# Object Oriented Programming with Java

## Unit – 1 SYLLABUS

Introduction: Why Java, History of Java, JVM, JRE, Java Environment, Java Source File
Structure, and Compilation Fundamental

Programming Structures in Java: Defining Classes in Java, Constructors, Methods, Access
Specifies, Static Members, Final Members, Comments, Data types, Variables, Operators,
Control Flow, Arrays & String.

Object Oriented Programming: Class, Object, Inheritance Super Class, Sub Class, Overriding,
Overloading, Encapsulation, Polymorphism, Abstraction, Interfaces, and Abstract Class.

Packages: Defining Package, CLASSPATH Setting for Packages, Making JAR Files for
Library Packages, Import and Static Import Naming Convention For Packages processor
evolution and types, microprocessor architecture and operation of its components, addressing
modes, interrupts, data transfer schemes, instruction and data flow, timer and timing diagram,
Interfacing devices.

#### History of Java

 Java is a high-level, object-oriented programming language developed by Sun
Microsystems (now owned by Oracle Corporation).
 Its history dates back to the early 1990s when a team led by James Gosling at Sun
Microsystems began developing a language for consumer electronics.
 The project was initially called _Oak_, named after an oak tree that stood outside
Gosling's office.
 However, due to trademark issues, the name was changed to _Java_ in 1995. Java was
designed with the intention of being platform-independent, meaning that Java programs
could run on any device with a Java Virtual Machine (JVM), regardless of the underlying
hardware and operating system. This was achieved by compiling Java code into an
intermediate bytecode, which could then be executed on any system with a JVM
installed.
 The language gained popularity rapidly, especially with the growth of the internet in the
mid to late 1990s.
 Java's portability made it an ideal choice for web development, and it became widely
used for building applets, which were small programs that could be embedded within web
pages to provide interactive content. In 2004, Sun Microsystems released the Java
platform as open source under the GNU General Public License (GPL), making it freely
available to developers. This move further fueled the adoption of Java and encouraged
the development of a vibrant ecosystem of libraries, frameworks, and tools.
 Over the years, Java has evolved through several versions, with each release introducing
new features, improvements, and optimizations.
 Oracle Corporation acquired Sun Microsystems in 2010, becoming the steward of the
Java platform. Today, Java remains one of the most popular programming languages in
the world, used in a wide range of applications, including web development, mobile app
development (Android apps are primarily written in Java), enterprise software, and
scientific computing.

#### Architecture of Java with Relation of JVM and JRE

The architecture of Java revolves around the Java Virtual Machine (JVM) and the Java Runtime
Environment (JRE), which are crucial components for running Java applications.

Java Virtual Machine (JVM):
 The JVM is a crucial part of the Java platform. It's an abstract computing machine
that enables Java bytecode to be executed on any hardware platform. When you
compile Java source code, it's translated into bytecode, which is a platform-
independent intermediate representation of the program.
 The JVM is responsible for interpreting or compiling this bytecode into machine
code that the underlying hardware can execute. It provides various services during
execution, including memory management, garbage collection, security, and
exception handling.
 The JVM specification is defined by Oracle, and there are implementations of the
JVM for various platforms, including Oracle's HotSpot, OpenJ9, and others.

Java Runtime Environment (JRE):
 The JRE is a package of software components that are necessary to run Java
applications. It includes the JVM, class libraries, and other supporting files.
 The JRE does not contain development tools such as compilers and debuggers; it's
purely for running Java applications.
 When you install Java on your system, you typically install the JRE, which allows
you to execute Java programs.

The relationship between JVM and JRE can be summarized as follows:
 The JRE includes the JVM along with necessary class libraries and other files required
for running Java applications. The JVM is the runtime engine that executes Java
bytecode, and it's a part of the JRE.
 Without the JVM, the JRE would not be able to run Java applications, as the JVM is
responsible for translating bytecode into machine code and managing the execution of
Java programs. The JVM and JRE work together to enable the execution of Java
applications on various hardware and operating system platforms, providing the key
elements necessary for the "write once, run anywhere" principle of Java.

#### Structure of Java Source File

The structure of a Java source file follows a specific format that includes various elements
required for defining classes, methods, variables, and other components of a Java program.
Here's a typical structure of a Java source file:

Package Declaration (Optional):
 A package declaration, if present, specifies the package to which the Java file
belongs. Packages are used to organize related classes and prevent naming
conflicts.
 Syntax: `package package_name;`
 Example: `package com.example.myproject;`

Import Statements (Optional):
 Import statements allow you to use classes from other packages without fully
qualifying their names.
 Syntax: `import package_name.ClassName;`
 Example: `import java.util.ArrayList;`

Class Declaration:
 A Java source file typically contains one or more class declarations. Each
class declaration defines a new class.
 Syntax: `access_modifier class ClassName { ... }`
 Example: `public class MyClass { ... }`

Class Body:
 The class body contains the members of the class, including fields, methods,
constructors, and nested classes/interfaces/enums.
 Fields: Variables that represent the state of the object.
 Methods: Functions that define the behavior of the object.
 Constructors: Special methods used for initializing objects.
 Nested Classes/Interfaces/Enums: Classes, interfaces, or enums defined within the
scope of the enclosing class.
Example:

```java
public class MyClass {
// Fields
private int field1;
private String field2;

// Constructor
public MyClass(int field1, String field2) {
this.field1 = field1;
this.field2 = field2;
}

// Methods
public void method1() {


// Method body
}
}
```

Comments:
 Comments are used to add explanations or documentation to the code. They are
ignored by the compiler.
 Single-Line Comments: `// This is a single-line comment`
 Multi-Line Comments: `/* This is a multi-line comment */`

Annotations (Optional):
 Annotations provide metadata about classes, methods, fields, etc., and are used
for various purposes like compile-time checks, code generation, and runtime
processing.
Example: `@Override`, `@Deprecated`

A complete Java source file may include some or all of these elements, depending on the
requirements of the program. However, the minimum requirement is typically the class
declaration and its body.

#### Data Types in Java

Java supports a rich set of data types that are classified into two categories: primitive data
types and reference data types.

Primitive Data Types:
 Primitive data types represent basic values and are predefined by the Java
language. They are not objects.
There are eight primitive data types in Java:

```
 boolean: Represents a boolean value (`true` or `false`).
 byte: Represents an 8-bit integer value.
 short: Represents a 16-bit integer value.
 int: Represents a 32-bit integer value.
 long: Represents a 64-bit integer value.
 float: Represents a single-precision 32-bit floating-point value.
 double: Represents a double-precision 64-bit floating-point value.
 char: Represents a single 16-bit Unicode character.
```

- Example:

```java
boolean bool = true;
byte b = 100;
short s = 1000;
int i = 100000;
long l = 10000000000L;
float f = 3.14f;
double d = 3.14159;
char ch = 'A';
```

Reference Data Types:

- Reference data types represent complex data structures and objects. They refer to objects
  created using classes.
- Reference data types include:
- Class Types: Objects of user-defined classes.
- Array Types: Arrays, which are ordered collections of elements of a specific type.
- Interface Types: Objects of interface types, which define a set of methods that a class must
  implement.
- Enumeration Types: Enumerated types, which define a fixed set of constants.

- Example:

```java
String str = "Hello, Java!";
MyClass obj = new MyClass();
int[] arr = {1, 2, 3, 4, 5};
```

     In addition to these data types, Java also supports type conversion, including widening
       conversion (implicit) and narrowing conversion (explicit).
     Widening conversion involves converting a smaller data type to a larger data type, while
       narrowing conversion involves converting a larger data type to a smaller data type. Java
       provides automatic conversion for widening conversions and requires explicit casting for
       narrowing conversions to avoid data loss.

#### Operators in Java

In Java, operators are symbols used to perform operations on operands. Operands can be
variables, literals, method calls, or expressions. Java supports a wide range of operators, which
can be classified into several categories:

Arithmetic Operators:

- Arithmetic operators perform basic arithmetic operations such as addition, subtraction,
  multiplication, division, and remainder.
- `+` (addition), `-` (subtraction), `*` (multiplication), `/` (division), `%` (remainder or
  modulo)
- Example:

```java
int a = 10, b = 3;
int sum = a + b; // Addition
int difference = a - b; // Subtraction


int product = a * b; // Multiplication
int quotient = a / b; // Division
int remainder = a % b; // Remainder
```

Assignment Operators:

- Assignment operators are used to assign values to variables.
- `=` (simple assignment), `+=`, `-=`, `*=`, `/=`, `%=` (compound assignment)
- Example:

```java
int x = 10;
x += 5; // Equivalent to: x = x + 5;
```

Comparison Operators:

- Comparison operators are used to compare two values and return a boolean result (`true` or
  `false`).
- `==` (equal to), `!=` (not equal to), `>` (greater than), `<` (less than), `>=` (greater than or
  equal to), `<=` (less than or equal to)
- Example:

```java
int a = 10, b = 5;
boolean isEqual = (a == b); // false
boolean isGreater = (a > b); // true
```

Logical Operators:

- Logical operators are used to perform logical operations on boolean values.
- `&&` (logical AND), `||` (logical OR), `!` (logical NOT)
- Example:

```java
boolean condition1 = true, condition2 = false;
boolean result = (condition1 && condition2); // false
```

Increment and Decrement Operators:

- Increment and decrement operators are used to increase or decrease the value of a variable
  by 1.
- `++` (increment), `--` (decrement)
- Example:

```java
int x = 5;
x++; // Increment x by 1
```

Bitwise Operators:

- Bitwise operators perform operations at the bit level on integer operands.
- `&` (bitwise AND), `|` (bitwise OR), `^` (bitwise XOR), `~` (bitwise complement), `<<` (left
  shift), `>>` (right shift), `>>>` (unsigned right shift)
- Example:

```java
int a = 5, b = 3;
int result = a & b; // Bitwise AND
```

Conditional Operator (Ternary Operator):

- The conditional operator `? :` is a ternary operator that evaluates a boolean expression and
  returns one of two values based on the result of the evaluation.
- Example:

```java
int x = 10;
String result = (x > 5)? "Greater than 5" : "Less than or equal to 5";
```

#### Classes in Java

In Java, a class is a blueprint or template for creating objects. It defines the properties (fields)
and behaviors (methods) that objects of that type will have. Here are the key aspects of a class
in Java:

Fields (Variables):

- Fields represent the state of an object. They define the data that an object holds.
- Fields can be of various data types, such as primitive types (int, double, boolean, etc.) or
  reference types (objects of other classes).
- Example:

```java
public class MyClass {
// Fields
private int age;
private String name;
}
```

Methods (Functions):

- Methods define the behavior of an object. They represent actions that the object can
  perform.
- Methods can have parameters (inputs) and return values (outputs), or they can be void (no
  return value).
- Example:

```java
public class MyClass {
// Method with parameters and return value
public int calculateSum(int a, int b) {
return a + b;
}

// Void method
public void displayInfo() {
System.out.println("This is MyClass");
}
}
```

Constructors:

- Constructors are special methods used for initializing objects. They are called when an
  object is created using the `new` keyword.
- Constructors have the same name as the class and may have parameters.
  Example:

```java
public class MyClass {
// Constructor with parameters
public MyClass(int age, String name) {


this.age = age;
this.name = name;
}
}
```

Access Modifiers:

- Access modifiers control the visibility of class members (fields, methods, constructors) from
  other classes.
- The four access modifiers in Java are `public`, `protected`, `default` (no modifier), and
  `private`.
  Example:

```java
public class MyClass {
// Public field
public int age;

// Private field
private String name;

// Public method
public void displayInfo() {
System.out.println("Name: " + name + ", Age: " + age);
}
}
```

Encapsulation:

- Encapsulation is the practice of bundling the data (fields) and methods that operate on the
  data within a single unit (class).
- It helps in controlling access to the data and ensures that the internal state of an object is
  consistent.
  Example:

```java
public class MyClass {
private int age;
private String name;

// Getters and setters for encapsulation
public int getAge() {
return age;
}

public void setAge(int age) {
this.age = age;
}

public String getName() {
return name;
}

public void setName(String name) {
this.name = name;
}
}
```

Classes are fundamental building blocks in Java programming and are used extensively to
create objects, encapsulate data, and define reusable components in Java applications.

#### Static Members

Static members in Java are class members that belong to the class itself rather than to instances
(objects) of the class. This means that there is only one copy of a static member, regardless of
how many instances of the class are created. Static members are associated with the class's
definition rather than with any specific instance of the class. Here are the types of static
members commonly used in Java:

Static Variables (Class Variables):

- Static variables are declared using the `static` keyword within a class.
- They are shared among all instances (objects) of the class.
- Static variables are initialized only once, at the start of the execution, and retain their values
  throughout the program's lifespan.
- They can be accessed directly using the class name or through an object reference.
  Example:

```java
public class MyClass {
// Static variable
public static int count = 0;
}
```

Static Methods:

- Static methods are also declared using the `static` keyword within a class.
- They belong to the class rather than to any specific instance, so they can be called without
  creating an object of the class.

- Static methods can only access static variables and other static methods directly. They
  cannot access instance variables or instance methods without an object reference.
  Example:

```java
public class MyClass {
// Static method
public static void printCount() {
System.out.println("Count: " + count);
}
}
```

Static Initialization Blocks:

- Static initialization blocks are used to initialize static variables of a class.
- They are executed only once when the class is loaded into the JVM.
- Static initialization blocks are defined using the `static` keyword followed by curly braces
  containing initialization code.
  Example:

```java
public class MyClass {
// Static variable
public static int count;

// Static initialization block
static {
count = 10;
}
}
```

Static members are useful for defining constants, utility methods, or shared resources that are
common to all instances of a class. However, they should be used judiciously, as they can lead
to tight coupling and make code harder to maintain if overused.

#### Control Statements or Structures in Java

Control statements in Java are used to control the flow of execution in a program. They allow
you to make decisions, iterate over code blocks, and execute statements based on certain
conditions. Java provides several types of control statements:

Conditional Statements:
if-else: Executes a block of code if a specified condition is true, and optionally executes a
different block of code if the condition is false.

```java
if (condition) {
// Code block to execute if condition is true
} else {
// Code block to execute if condition is false
}
```

switch-case: Evaluates an expression and executes code blocks based on matching case
values.

```java
switch (expression) {
case value1:
// Code block to execute if expression matches value
break;
case value2:


// Code block to execute if expression matches value
break;
default:
// Code block to execute if expression doesn't match any case
}
```

Looping Statements:
for: Executes a block of code repeatedly for a specified number of times.

```java
for (initialization; condition; update) {
// Code block to execute
}
```

while: Executes a block of code repeatedly as long as a specified condition is true.

```java
while (condition) {
// Code block to execute
}
```

do-while: Executes a block of code once, and then repeatedly executes the block as long as a
specified condition is true.

```java
do {
// Code block to execute
} while (condition);
```

Branching Statements:
break: Terminates the execution of a loop or switch statement.
continue: Skips the current iteration of a loop and proceeds to the next iteration.
return: Terminates the execution of a method and returns a value (if any) to the caller.

Enhanced for-loop:

- Iterates over elements of an array or collection sequentially without explicitly using an index
  variable.

```java
for (type element : array) {
// Code block to execute for each element
}
```

Control statements are fundamental for creating flexible and efficient Java programs. They
allow you to implement conditional logic, looping constructs, and branching behavior, enabling
you to write programs that can adapt to different scenarios and conditions.

#### Arrays in Java

Arrays in Java are used to store multiple values of the same type under a single variable name.
They provide a convenient way to work with collections of data of the same type. Here's an
overview of arrays in Java:
Array Declaration:

- To declare an array in Java, you specify the type of elements the array will hold, followed by
  square brackets `[]`, and then the array name.
  Example:

```java
// Declaration of an array of integers
int[] numbers;
```

Array Initialization:

- Arrays can be initialized either at the time of declaration or later using the `new` keyword.
  Example:

```java
// Initialization at the time of declaration
int[] numbers = {1, 2, 3, 4, 5};

// Initialization after declaration
int[] numbers = new int[5]; // Array of 5 integers, initialized with default values (0)
```

Accessing Array Elements:

- Array elements are accessed using an index, which starts from 0 for the first element and
  increments by 1 for each subsequent element.
  Example:

```java
int[] numbers = {1, 2, 3, 4, 5};
int firstElement = numbers[0]; // Accessing the first element
int thirdElement = numbers[2]; // Accessing the third element
```

Array Length:

- You can determine the length (number of elements) of an array using the `length` property.
  Example:

```java
int[] numbers = {1, 2, 3, 4, 5};
int length = numbers.length; // Length of the array
```

Iterating Over Arrays:

- Arrays can be iterated using loops such as `for` loops or enhanced `for` loops.
  Example using a `for` loop:

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int i = 0; i < numbers.length; i++) {
System.out.println(numbers[i]);
}
```

Example using an enhanced `for` loop:

```java
int[] numbers = {1, 2, 3, 4, 5};
for (int number : numbers) {
System.out.println(number);
}
```

Multidimensional Arrays:

- Java supports multidimensional arrays, which are arrays of arrays.
  Example:

```java
int[][] matrix = {
{1, 2, 3},
{4, 5, 6},
{7, 8, 9}
};
```

Arrays are versatile data structures in Java and are widely used in programming for storing and
manipulating collections of data efficiently.

#### String class in Java

The `String` class in Java is a fundamental class for working with strings, which are sequences
of characters. It provides a wide range of methods for string manipulation, comparison,
searching, and extraction. Here are some important members and methods of the `String` class
in Java:
Constructor:

- `String()`: Constructs an empty string.
- `String(String original)`: Constructs a new string with the same contents as the specified
  string.
- `String(char[] value)`: Constructs a new string whose value is the specified character array.
- `String(char[] value, int offset, int count)`: Constructs a new string whose value is a
  substring of the specified character array.

Instance Methods:

- `length()`: Returns the length of the string.
- `charAt(int index)`: Returns the character at the specified index.
- `indexOf(int ch)`: Returns the index of the first occurrence of the specified character, or - 1
  if the character is not found.
- `indexOf(int ch, int fromIndex)`: Returns the index of the first occurrence of the specified
  character, starting the search at the specified index.
- `indexOf(String str)`: Returns the index of the first occurrence of the specified substring, or
- 1 if the substring is not found.
- `indexOf(String str, int fromIndex)`: Returns the index of the first occurrence of the
  specified substring, starting the search at the specified index.
- `substring(int beginIndex)`: Returns a substring of the string starting from the specified
  index.
- `substring(int beginIndex, int endIndex)`: Returns a substring of the string starting from
  the specified begin index and ending at the specified end index.

- `toLowerCase()`: Converts all characters in the string to lowercase.
- `toUpperCase()`: Converts all characters in the string to uppercase.
- `trim()`: Removes leading and trailing whitespace from the string.
- `split(String regex)`: Splits the string into an array of substrings based on the specified
  regular expression.
- `startsWith(String prefix)`: Returns true if the string starts with the specified prefix.
- `endsWith(String suffix)`: Returns true if the string ends with the specified suffix.
- `equals(Object anObject)`: Compares this string to the specified object.
- `equalsIgnoreCase(String anotherString)`: Compares this string to another string,
  ignoring case considerations.
- `compareTo(String anotherString)`: Compares two strings lexicographically.
- `concat(String str)`: Concatenates the specified string to the end of this string.

Static Methods:

- `valueOf(boolean b)`: Returns the string representation of the boolean argument.
- `valueOf(char c)`: Returns the string representation of the char argument.
- `valueOf(int i)`: Returns the string representation of the int argument.
- `valueOf(long l)`: Returns the string representation of the long argument.
- `valueOf(float f)`: Returns the string representation of the float argument.
- `valueOf(double d)`: Returns the string representation of the double argument.
- `valueOf(Object obj)`: Returns the string representation of the Object argument.

The `String` class in Java is immutable, meaning once a `String` object is created, its value
cannot be changed. However, many `String` methods return a new `String` object with the
modified value. Understanding and effectively using the methods provided by the `String` class
are essential for string manipulation in Java.

#### OOPs Concepts in Java

Java is a widely-used object-oriented programming language, and it embodies many key object-
oriented concepts. Here's an overview of some of these concepts:
Classes and Objects:

- Classes are blueprints for creating objects. They define the properties (fields) and behaviors
  (methods) of objects.
- Objects are instances of classes. They represent real-world entities and have state and
  behavior.
  Example:

```java
// Class definition
public class Car {
// Fields
private String model;
private int year;
// Constructor
public Car(String model, int year) {
this.model = model;
this.year = year;
}
// Method
public void drive() {
System.out.println("The car is driving.");
}
}
// Object creation
Car myCar = new Car("Toyota", 2022);
```

Encapsulation:

- Encapsulation is the bundling of data (fields) and methods that operate on the data within a
  single unit (class).
- It hides the internal state of objects and restricts direct access to the data, providing
  controlled access through methods.
  Example:

```java
public class BankAccount {
private double balance;

public void deposit(double amount) {
balance += amount;
}

public double getBalance() {
return balance;
}
}
```

Inheritance:

- Inheritance is a mechanism where a new class (subclass or derived class) is derived from an
  existing class (superclass or base class).
- The subclass inherits the fields and methods of the superclass and can add its own fields and
  methods.
- It promotes code reusability and establishes a parent-child relationship between classes.
- Example:

```java


// Superclass
public class Animal {
public void eat() {
System.out.println("Animal is eating.");
}
}

// Subclass
public class Dog extends Animal {
public void bark() {
System.out.println("Dog is barking.");
}
}
```

Polymorphism:

- Polymorphism allows objects of different classes to be treated as objects of a common
  superclass through inheritance.
- It enables methods to be overridden in subclasses to provide different implementations.
- Polymorphism is achieved through method overriding and method overloading.
  Example:

```java
// Superclass
public class Shape {
public void draw() {
System.out.println("Drawing a shape.");
}
}


// Subclasses
public class Circle extends Shape {
@Override
public void draw() {
System.out.println("Drawing a circle.");
}
}

public class Rectangle extends Shape {
@Override
public void draw() {
System.out.println("Drawing a rectangle.");
}
}
```

Abstraction:

- Abstraction is the concept of hiding the complex implementation details and showing only
  the essential features of an object.
- It provides a simplified view of objects and allows users to focus on what an object does
  rather than how it does it.
- Abstraction is achieved through abstract classes and interfaces.
  Example:

```java
// Abstract class
public abstract class Shape {
public abstract void draw();
}


// Concrete subclass
public class Circle extends Shape {
@Override
public void draw() {
System.out.println("Drawing a circle.");
}
}
```

These are some of the core object-oriented concepts in Java that are essential for building
modular, reusable, and maintainable software applications. Understanding and effectively
applying these concepts are key to writing efficient and scalable Java programs.

#### Packages in Java

In Java, packages are used to organize classes into namespaces, providing a way to group
related classes and prevent naming conflicts. Packages help in organizing large codebases and
promote modularity and code reuse. Here's an overview of the package concept and access
modifiers in Java:

### Packages:

Package Declaration:

- At the beginning of a Java source file, you can declare the package to which the class
  belongs using the `package` keyword followed by the package name.
- Example:

```java
package com.example.myproject;
```

Package Structure:

- Packages are organized hierarchically, with each level separated by a dot (`.`).
- For example, `com.example.myproject` represents a package named `myproject` inside the
  `example` package inside the `com` package.

Package Visibility:

- Classes within the same package can access each other without any restrictions.
- Classes from different packages can access public and protected members of each other's
  classes.
- Classes from different packages cannot access default (package-private) and private
  members of each other's classes.

Import Statement:

- To use classes from other packages in your code, you can use the `import` statement to
  specify the fully qualified name of the class or package.
  Example:

```java
import java.util.ArrayList;
```

#### Access Modifiers

Public:

- Members (classes, fields, methods, constructors) with the `public` modifier are accessible
  from any other class, regardless of the package.
  Example:

```java
public class MyClass {


public void myMethod() {
// Method body
}
}
```

Protected:

- Members with the `protected` modifier are accessible within the same package or by
  subclasses (even if they are in different packages).
  Example:

```java
protected class MyClass {
protected void myMethod() {
// Method body
}
}
```

Default (Package-Private):

- Members with no access modifier (default) are accessible only within the same package.
  Example:

```java
class MyClass {
void myMethod() {
// Method body
}
}
```

Private:

- Members with the `private` modifier are accessible only within the same class.
  Example:

```java
public class MyClass {
private int myField;

private void myMethod() {
// Method body
}
}
```

Understanding and appropriately using packages and access modifiers are essential for
designing well-structured and maintainable Java applications. They help in managing the
visibility and accessibility of classes and members, ensuring encapsulation and modularization
of code.

#### CLASSPATH Setting for Package

In Java, the CLASSPATH environment variable is used to specify the locations where Java
should look for classes and packages when executing Java programs. When you create your
own packages and want Java to locate them during compilation and execution, you need to set
the CLASSPATH appropriately. Here's how you can set the CLASSPATH for your packages:

##### Setting CLASSPATH for Packages:

Understanding Package Structure:

- Before setting the CLASSPATH, ensure that you understand the directory structure of your
  packages.
- Java follows a convention where the directory structure reflects the package structure. For
  example, a class in the package `com.example.myproject` should be located in a directory
  named `com/example/myproject`.

Compile with Correct Directory Structure:

- When compiling Java source files that belong to packages, make sure to maintain the correct
  directory structure.
- For example, if your source file `MyClass.java` belongs to the package `com.example`, the
  source file should be located in the directory `com/example`.

Setting CLASSPATH:

- You can set the CLASSPATH environment variable using command-line options or by
  modifying system environment variables.
- To include the current directory (where your compiled classes are located) and additional
  directories containing classes and packages, you can use the `-classpath` or `-cp` option when
  compiling and running Java programs.
- Example (using command line):

```bash
javac -classpath .:/path/to/other/directory MyClass.java
java -classpath .:/path/to/other/directory MyClass
```

- Alternatively, you can set the CLASSPATH environment variable directly:

```bash
export CLASSPATH=.:/path/to/other/directory
```

- Replace `/path/to/other/directory` with the actual path to the directory containing your
  package structure.

Multiple Directories and JAR Files:

- You can specify multiple directories and JAR files in the CLASSPATH separated by colon
  `:` on Unix-like systems or semicolon `;` on Windows.
  Example:

```bash
export CLASSPATH=.:/path/to/other/directory:/path/to/jarfile.jar
```

Permanent Setting (Optional):

- To make the CLASSPATH setting permanent, you can add it to your shell profile or
  environment configuration file (e.g., `.bashrc`, `.bash_profile` on Unix-like systems).
  Example (for Unix-like systems):

```bash
echo "export CLASSPATH=.:/path/to/other/directory" >> ~/.bashrc
source ~/.bashrc
```

By setting the CLASSPATH appropriately, Java will be able to locate and load classes and
packages from the specified directories and JAR files during compilation and execution,
including your own custom packages.

#### Making JAR Files for Library Packages

Creating JAR (Java ARchive) files is a common way to package Java classes and resources into
a single file for distribution or use as a library. Here's how you can make JAR files for your
library packages:

##### Steps to Create JAR Files for Library Packages:

1. Compile Your Classes:

- Compile your Java classes that belong to the library packages.
- Ensure that you maintain the correct directory structure matching the package structure.

2. Create Manifest File (Optional):

- If your JAR file needs a manifest file (for specifying the main class, version information,
  etc.), you can create one. Otherwise, Java will create a default manifest.
- Example `manifest.txt`:

```
Manifest-Version: 1.0
Main-Class: com.example.MainClass
```

3. Create JAR File:

- Use the `jar` command-line tool to create the JAR file.
- Syntax:

```bash
jar cvf jar-file-name.jar [options] [files/directories]
```

- Example:

```bash
jar cvf mylibrary.jar -C /path/to/classes.
```

- `-C /path/to/classes`: Specifies the directory containing compiled classes.
- `.`: Includes all files and directories in the current directory (including the directory
  structure).

4. Include Manifest (Optional):

- If you have a custom manifest file, you can include it in the JAR file using the `-m` option.
- Example:

```bash
jar cvfm mylibrary.jar /path/to/manifest.txt -C /path/to/classes.
```

5. Test Your JAR File:

- After creating the JAR file, you can test it by running Java programs that use classes from
  the library.
- Ensure that the JAR file is included in the classpath when compiling and running Java
  programs.
- Example (running a Java program):

```bash
java -cp mylibrary.jar:. com.example.MainClass
```

6. Distribute Your JAR File:

- Once your JAR file is created and tested, you can distribute it to other developers or users
  who want to use your library.
- They can include the JAR file in their classpath when compiling and running their Java
  programs.

By following these steps, you can create JAR files for your library packages, making it easier to
distribute and use your Java libraries in other projects.

### Import and Static Import Naming Convention For Packages

When importing classes or static members from packages in Java, it's important to follow
certain naming conventions to maintain code readability and consistency. Here are some
common naming conventions for import statements and static imports:

##### Import Statements:

Import Single Class:

- Import a single class from a package:

```java
import package.name.ClassName;
```

Import All Classes from a Package:

- Import all classes from a package (not recommended due to potential naming conflicts):

```java
import package.name.*;
```

Fully Qualified Class Names:

- Avoid using wildcards (`*`) in import statements for better clarity.
- Always use fully qualified class names if you have multiple classes with the same name in
  different packages.
- Example:

```java
import java.util.ArrayList;
import java.util.HashMap;
```

##### Static Import Statements:

1. Import Single Static Member:

- Import a single static member from a class:

```java
import static package.name.ClassName.staticMember;
```

2. Import All Static Members from a Class:

- Import all static members from a class (not recommended due to potential naming conflicts):

```java
import static package.name.ClassName.*;
```

#### Naming Conventions

Package Naming:

- Package names should be in lowercase letters.
- Use meaningful and descriptive names for packages, typically in reverse domain name
  format.
- Example:

```java
package com.example.myproject;
```

Class Naming:

- Class names should be in PascalCase (camel case with the first letter of each word
  capitalized).
- Use nouns or noun phrases that represent the class's purpose or functionality.

- Example:

```java
public class MyClass { ... }
```

Static Member Naming:

- Static member names should be in lowercase letters with words separated by underscores
  (`_`) for readability.
- Use descriptive names that indicate the purpose or functionality of the static member.
- Example:

```java
public static final int MAX_VALUE = 100;
```

Avoid Confusing Names:

- Avoid using names that are too generic or easily confused with standard Java classes or
  keywords.
- Use meaningful and descriptive names that convey the intended functionality clearly.
- Example:

```java
import java.util.List; // Good
import java.util.LinkedList; // Better
```

Following these naming conventions helps maintain consistency and clarity in your Java code,
making it easier to read, understand, and maintain.

# Thank You
