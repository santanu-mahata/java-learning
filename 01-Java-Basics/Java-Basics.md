# ☕ Java Basics

Java is a **high-level, object-oriented programming language** used to
build applications, backend systems, and many other types of software.

------------------------------------------------------------------------

## 1. First Java Program

``` java
class Main {
    public static void main(String[] args) {
        System.out.println("Hello Java");
    }
}
```

### Understand it

-   `class Main` → creates a class named `Main`
-   `main()` → program execution starts here
-   `System.out.println()` → prints something on the screen

Output:

``` text
Hello Java
```

------------------------------------------------------------------------

## 2. Variable

A variable is a place where we **store data**.

``` java
int age = 22;
String name = "Santanu";
```

Here:

-   `int` → data type
-   `age` → variable name
-   `22` → value

Example:

``` java
class Main {
    public static void main(String[] args) {

        int age = 22;
        String name = "Santanu";

        System.out.println(name);
        System.out.println(age);
    }
}
```

------------------------------------------------------------------------

## 3. Data Types

A data type tells Java **what type of data** a variable will store.

### Primitive Data Types

``` text
byte
short
int
long
float
double
char
boolean
```

Example:

``` java
int age = 22;
double price = 99.50;
char grade = 'A';
boolean isJavaEasy = true;
```

### Non-Primitive

Example:

``` java
String name = "Santanu";
```

------------------------------------------------------------------------

## 4. Operators

Operators are used for calculations and comparisons.

### Arithmetic Operators

``` java
int a = 10;
int b = 3;

System.out.println(a + b); // 13
System.out.println(a - b); // 7
System.out.println(a * b); // 30
System.out.println(a / b); // 3
System.out.println(a % b); // 1
```

### Comparison Operators

``` java
a > b
a < b
a == b
a != b
a >= b
a <= b
```

The result is either `true` or `false`.

------------------------------------------------------------------------

## 5. Taking Input

We commonly use `Scanner` to take input from the user.

``` java
import java.util.Scanner;

class Main {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter your age: ");
        int age = sc.nextInt();

        System.out.println("Your age is: " + age);
    }
}
```

### Common Scanner methods

``` java
nextInt()       // int
nextDouble()    // double
next()          // one word
nextLine()      // full line
```

------------------------------------------------------------------------

## 6. Type Casting

Converting one data type into another is called **type casting**.

### Widening Casting

Small type → bigger type

``` java
int a = 10;
double b = a;

System.out.println(b); // 10.0
```

### Narrowing Casting

Big type → smaller type

We need to manually cast it:

``` java
double a = 10.5;
int b = (int) a;

System.out.println(b); // 10
```

------------------------------------------------------------------------

## 7. if-else

`if-else` is used to check a condition.

``` java
int age = 20;

if(age >= 18) {
    System.out.println("Adult");
}
else {
    System.out.println("Not Adult");
}
```

### Multiple conditions

``` java
int marks = 75;

if(marks >= 90) {
    System.out.println("A");
}
else if(marks >= 60) {
    System.out.println("B");
}
else {
    System.out.println("C");
}
```

------------------------------------------------------------------------

## 8. switch

`switch` is useful when we have multiple fixed options.

``` java
int day = 2;

switch(day) {
    case 1:
        System.out.println("Monday");
        break;

    case 2:
        System.out.println("Tuesday");
        break;

    default:
        System.out.println("Invalid day");
}
```

Output:

``` text
Tuesday
```

------------------------------------------------------------------------

## 9. Loops

Loops are used when we want to **repeat the same work**.

### for loop

``` java
for(int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

Output:

``` text
1
2
3
4
5
```

### while loop

``` java
int i = 1;

while(i <= 5) {
    System.out.println(i);
    i++;
}
```

### do-while loop

In `do-while`, the condition is checked **after** the code runs.

So it will run at least once.

``` java
int i = 1;

do {
    System.out.println(i);
    i++;
} while(i <= 5);
```

------------------------------------------------------------------------

## 10. break and continue

### break

`break` completely stops the loop.

``` java
for(int i = 1; i <= 5; i++) {

    if(i == 3) {
        break;
    }

    System.out.println(i);
}
```

Output:

``` text
1
2
```

### continue

`continue` skips the current iteration.

``` java
for(int i = 1; i <= 5; i++) {

    if(i == 3) {
        continue;
    }

    System.out.println(i);
}
```

Output:

``` text
1
2
4
5
```

------------------------------------------------------------------------

## 11. Array

An array stores **multiple values of the same type**.

``` java
int[] marks = {80, 75, 90, 60};
```

Array index starts from `0`.

``` java
System.out.println(marks[0]); // 80
System.out.println(marks[2]); // 90
```

Array size:

``` java
System.out.println(marks.length);
```

Print all elements:

``` java
for(int i = 0; i < marks.length; i++) {
    System.out.println(marks[i]);
}
```

------------------------------------------------------------------------

## 12. String

`String` is used to store text.

``` java
String name = "Santanu";
```

Some useful methods:

``` java
name.length();
name.toUpperCase();
name.toLowerCase();
name.charAt(0);
name.equals("Santanu");
```

Example:

``` java
String name = "Santanu";

System.out.println(name.length());
System.out.println(name.toUpperCase());
System.out.println(name.charAt(0));
```

------------------------------------------------------------------------

## 13. Methods

A method is a block of code that performs a **specific task**.

``` java
class Main {

    static void greet() {
        System.out.println("Hello Santanu");
    }

    public static void main(String[] args) {
        greet();
    }
}
```

### Method with parameters

``` java
static void add(int a, int b) {
    System.out.println(a + b);
}

public static void main(String[] args) {
    add(10, 20);
}
```

Output:

``` text
30
```

### Method with return value

``` java
static int add(int a, int b) {
    return a + b;
}

public static void main(String[] args) {

    int result = add(10, 20);

    System.out.println(result);
}
```

------------------------------------------------------------------------

## 14. static

`static` means the member belongs to the **class**, rather than to a
particular object.

Example:

``` java
class Main {

    static int count = 10;

    public static void main(String[] args) {
        System.out.println(count);
    }
}
```

Static method:

``` java
static void show() {
    System.out.println("Hello");
}
```

Call:

``` java
show();
```

------------------------------------------------------------------------

## 15. final

`final` means the value cannot be changed after it is assigned.

``` java
final int AGE = 22;

// AGE = 25;  // Error
```

Easy way to remember:

**final = cannot be changed**

------------------------------------------------------------------------

## 16. Package and import

A package is used to **organize related classes**.

Example:

``` java
package mypackage;
```

To use a class from another package, we use `import`.

``` java
import java.util.Scanner;
```

------------------------------------------------------------------------

# 🧠 Quick Revision

  Topic          Easy Meaning
  -------------- -----------------------------------
  Variable       Stores data
  Data Type      Tells what type of data
  Operator       Performs calculation / comparison
  Scanner        Takes user input
  Type Casting   Converts one data type to another
  if-else        Checks conditions
  switch         Selects from fixed options
  Loop           Repeats a task
  break          Stops the loop
  continue       Skips current iteration
  Array          Stores multiple values
  String         Stores text
  Method         Performs a specific task
  static         Belongs to the class
  final          Value cannot be changed
  package        Organizes classes
  import         Allows us to use another class

------------------------------------------------------------------------

# 📌 Learning Order

``` text
Java Basics
    ↓
OOP
    ↓
Exception Handling
    ↓
Collections
    ↓
Generics
    ↓
Java 8+
    ↓
Multithreading
    ↓
SQL + JDBC
    ↓
Spring / Spring Boot
```

**Next → OOP**

