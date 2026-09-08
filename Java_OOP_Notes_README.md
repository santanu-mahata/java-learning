# Java OOP Notes

> These notes are converted from my handwritten notebook notes.\
> The order and simple explanation style are kept as close as possible
> to the original notes.

------------------------------------------------------------------------

## 1. User-Defined Class

A class which is created by a programmer is called a **user-defined
class**.

### Example

``` java
class ClassName {
    // variables
    // methods
}
```

------------------------------------------------------------------------

## 2. Object

An object is an **instance of a class**. Once the object is created, it
gets memory.

### Syntax

``` java
ClassName objName = new ClassName();
```

Here:

-   `ClassName` → class name
-   `objName` → object reference
-   `new` → creates/allocates the object
-   `ClassName()` → constructor call

### Example

``` java
class Demo {
    int a = 10;
    String b = "Santanu";

    void show() {
        System.out.println(a + " " + b);
    }
}

class Test {
    public static void main(String[] args) {
        Demo obj = new Demo();
        obj.show();
    }
}
```

------------------------------------------------------------------------

# Constructor

A constructor is a special type of method whose name is the **same as
the class name**.

### Main purpose

The main purpose of a constructor is to **initialize the object**.

### Important points from the notes

1.  Every Java class has a constructor.
2.  A constructor is automatically called at the time of object
    creation.
3.  A constructor does not have a return type.

### Syntax

``` java
class A {
    A() {
        // constructor code
    }
}
```

------------------------------------------------------------------------

## Types of Constructor

The notes cover these types:

1.  Private Constructor
2.  Default Constructor
3.  Parameterized Constructor
4.  Copy Constructor

------------------------------------------------------------------------

## 3. Default Constructor

A constructor which does not have any parameters is called a **default
constructor**.

### Syntax

``` java
class A {
    A() {
        // no parameters
    }
}
```

### Example

``` java
class A {

    int a;
    String b;

    A() {
        a = 100;
        b = "Santanu";
    }

    void show() {
        System.out.println(a + " " + b);
    }
}

class B {
    public static void main(String[] args) {

        A obj = new A();
        obj.show();

    }
}
```

### Note

If you do not write a constructor, Java can provide a default
constructor automatically (provided the class has no explicitly declared
constructor).

------------------------------------------------------------------------

## 4. Parameterized Constructor

A constructor through which we can pass one or more parameters is called
a **parameterized constructor**.

### Syntax

``` java
class A {

    int x;
    int y;

    A(int a, int b) {
        x = a;
        y = b;
    }
}
```

### Example

``` java
class A {

    int x;
    int y;

    A(int a, int b) {
        x = a;
        y = b;
    }

    void show() {
        System.out.println(x + " " + y);
    }
}

class B {
    public static void main(String[] args) {

        A obj = new A(100, 200);
        obj.show();

    }
}
```

------------------------------------------------------------------------

## 5. Private Constructor

In Java, it is possible to write a constructor as `private`.

A private constructor cannot be accessed directly from outside the
class.

### Syntax

``` java
class A {

    private A() {
        // constructor code
    }
}
```

------------------------------------------------------------------------

## 6. Constructor Overloading

When a class contains **more than one constructor with different
parameters**, it is called constructor overloading.

### Example

``` java
class A {

    int a;
    double b;
    String c;

    A() {
        a = 100;
        b = 15.32;
        c = "Santanu";
    }

    A(int x) {
        a = x;
    }

    A(double y, String z) {
        b = y;
        c = z;
    }
}
```

The constructors have the same name but different parameter lists.

------------------------------------------------------------------------

## 7. Copy Constructor

Whenever we pass an **object reference** to a constructor, it is called
a copy constructor in these notes.

### Example

``` java
class A {

    int a;
    String b;

    A(int a, String b) {
        this.a = a;
        this.b = b;
    }

    A(A obj) {
        this.a = obj.a;
        this.b = obj.b;
    }
}
```

### Creating objects

``` java
A obj1 = new A(100, "Santanu");
A obj2 = new A(obj1);
```

Here `obj2` gets values from `obj1`.

------------------------------------------------------------------------

# Static Block

A **static block** is a block of code that is executed when the class is
loaded.

### Syntax

``` java
class A {

    static {
        System.out.println("Class loading");
    }

    public static void main(String[] args) {
        A obj = new A();
    }
}
```

### Flow from the notes

``` text
.java file
   ↓
javac
   ↓
.class file
   ↓
Class Loader
   ↓
Bytecode Verifier
   ↓
Execution Engine
   ↓
JVM
```

The static block is associated with class loading.

------------------------------------------------------------------------

# Instance Block

An **instance block** is a block of code inside a class without a name.

### Syntax

``` java
class A {

    {
        // instance block code
    }
}
```

### Important points

1.  Instance block executes before the constructor.
2.  Instance variables can be used inside the instance block.
3.  It can be used for common initialization code.

### Example

``` java
class A {

    int a = 10;

    {
        System.out.println("Instance block");
    }

    A() {
        System.out.println("Constructor");
    }
}
```

------------------------------------------------------------------------

# Inheritance

Inheritance is a mechanism through which a **child class can acquire the
properties and methods of a parent class**.

### Example

``` java
class Parent {
    int a = 10;

    void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    int b = 20;

    void display() {
        System.out.println("Child");
    }
}
```

Here:

``` text
Parent
   ↑
Child
```

`Child` can use the accessible members of `Parent`.

------------------------------------------------------------------------

## Types of Inheritance

The notes mention:

1.  Single inheritance
2.  Multilevel inheritance
3.  Multiple inheritance
4.  Hybrid inheritance

### Single inheritance

``` text
A
↑
B
```

One child class inherits from one parent class.

### Multilevel inheritance

``` text
A
↑
B
↑
C
```

A class inherits from another child class.

### Multiple inheritance

One class having multiple parent classes.

> In Java, multiple inheritance through classes is not supported. It can
> be achieved through interfaces.

### Hybrid inheritance

A combination of different types of inheritance.

------------------------------------------------------------------------

# `super` Keyword

The `super` keyword refers to the **immediate parent class object**.

### Uses from the notes

1.  To access parent-class variables.
2.  To call parent-class methods.
3.  To call the parent-class constructor.

### Example

``` java
class A {

    int x = 10;

    void show() {
        System.out.println("Parent");
    }
}

class B extends A {

    int x = 20;

    void display() {

        System.out.println(super.x);
        super.show();

    }
}
```

------------------------------------------------------------------------

# `this` Keyword

The `this` keyword refers to the **current object**.

### Example

``` java
class A {

    int a;

    A(int a) {
        this.a = a;
    }
}
```

Here:

``` java
this.a
```

refers to the current object's variable.

### Common use

`this` is especially useful when the instance variable and parameter
have the same name.

------------------------------------------------------------------------

# Polymorphism

**Polymorphism** means **one name, many forms**.

The notes divide polymorphism into:

``` text
Polymorphism
     ↓
Compile-time polymorphism
Runtime polymorphism
```

------------------------------------------------------------------------

## Compile-Time Polymorphism

Compile-time polymorphism is achieved through **method overloading**.

### Method Overloading

When a class contains more than one method with the **same name but
different parameters**, it is called method overloading.

### Example

``` java
class A {

    void add(int x, int y) {
        System.out.println(x + y);
    }

    void add(int x, double y) {
        System.out.println(x + y);
    }
}
```

Here both methods are named `add`, but their parameter lists are
different.

### Important point

Changing only the return type does **not** create method overloading.

------------------------------------------------------------------------

## Runtime Polymorphism

Runtime polymorphism is associated with **method overriding**.

It happens when a child class provides its own implementation of a
method already defined in the parent class.

### Basic idea

``` java
class Parent {

    void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {

    @Override
    void show() {
        System.out.println("Child");
    }
}
```

When the overridden method is called through a parent reference, the
method that runs can depend on the actual object at runtime.

------------------------------------------------------------------------

# Abstraction

The notes define abstraction as hiding implementation details and
showing the required functionality.

Abstraction can be achieved using:

``` text
1. Abstract class
2. Interface
```

------------------------------------------------------------------------

# Abstract Method

A method which contains the `abstract` keyword at the time of
declaration is called an **abstract method**.

### Syntax

``` java
abstract void show();
```

An abstract method does not have a method body.

### Important points from the notes

1.  An abstract method is used inside an abstract class.
2.  It does not contain a body.
3.  It ends with `;`.
4.  A subclass must provide the implementation of the abstract method.

### Example

``` java
abstract class A {

    abstract void show();

}
```

A child class can implement it:

``` java
class B extends A {

    @Override
    void show() {
        System.out.println("Hello");
    }
}
```

------------------------------------------------------------------------

# Interface

An interface is like a class in structure, but in the basic form used in
these notes it contains abstract methods and constants.

Java provides the `implements` keyword to implement an interface.

### Example

``` java
interface Client {

    void run();

}

class Developer implements Client {

    public void run() {
        System.out.println("Running");
    }
}
```

### Important points from the notes

1.  Interface methods are, by default, `public` and `abstract` (for
    abstract methods).
2.  Interface variables are, by default, `public`, `static`, and
    `final`.
3.  Interface methods must be implemented/overridden in the implementing
    class.
4.  The interface acts as a contract between the client and developer.

------------------------------------------------------------------------

# OOP Features Mentioned in the Notes

``` text
OOP
│
├── Class
├── Object
├── Inheritance
├── Polymorphism
├── Encapsulation
└── Abstraction
```

The uploaded notes list **encapsulation**, but the provided pages do not
contain a separate detailed explanation/example for it.

------------------------------------------------------------------------

# Quick Revision

  -----------------------------------------------------------------------
  Topic                               Simple Meaning
  ----------------------------------- -----------------------------------
  Class                               Blueprint / logical entity used to
                                      define objects

  Object                              Instance of a class

  Constructor                         Initializes an object

  Default Constructor                 Constructor with no parameters

  Parameterized Constructor           Constructor with parameters

  Copy Constructor                    Constructor receiving another
                                      object

  Static Block                        Runs during class loading

  Instance Block                      Runs before constructor when an
                                      object is created

  Inheritance                         Child acquires accessible
                                      properties/methods from parent

  `super`                             Refers to the immediate parent

  `this`                              Refers to the current object

  Polymorphism                        One name, many forms

  Overloading                         Same method name, different
                                      parameters

  Overriding                          Child provides its own version of
                                      parent method

  Abstraction                         Hiding implementation details

  Abstract Method                     Method declared without
                                      implementation

  Interface                           Contract implemented by a class
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## My Learning Order

``` text
Class & Object
      ↓
Constructor
      ↓
Default / Parameterized / Private / Copy
      ↓
Constructor Overloading
      ↓
Static Block
      ↓
Instance Block
      ↓
Inheritance
      ↓
super
      ↓
this
      ↓
Polymorphism
      ↓
Method Overloading
      ↓
Method Overriding
      ↓
Abstraction
      ↓
Abstract Method
      ↓
Interface
```
