# Exception Handling

## 1. Exception

An exception is unexpected, unwanted abnormal situation that caused at
program called exception.

### What is Exception Handling?

In exception handling, we should have an alternate source through which
we can handle the exception.

### Java provides some mechanisms to work with exception

1.  try
2.  catch
3.  throw
4.  throws
5.  finally

------------------------------------------------------------------------

# 2. Exception Hierarchy

Throwable class is the super or root class of Java exception hierarchy
which contains two sub classes:

1.  Exception
2.  Errors

``` text
                    Throwable
                    /       \
             Exception      Errors
```

### Exception

-   Runtime Exception
-   IO Exception
-   SQL Exception
-   Interrupted Exception
-   Class Not Found Exception

### Errors

-   Stack Overflow Error
-   Out of Memory Error
-   IO Error
-   Linkage Error

### Runtime Exception

-   Arithmetic Exception
-   NullPointer Exception
-   Number Format Exception
-   Index Out Of Bounds Exception
    -   Array Index Out Of Bounds Exception
    -   String Index Out Of Bounds Exception

------------------------------------------------------------------------

# 3. Java Exception Flow

``` text
Test.java
   ↓
javac
   ↓
Errors

Test.class
   ↓
JVM
   ↓
Exception / Errors
```

Java provides some mechanism to work with exception:

``` text
1. try
2. catch
3. throw
4. throws
5. finally
```

------------------------------------------------------------------------

# 4. NullPointerException

``` java
class NPE {
    public static void main(String[] args) {

        String str = null;

        try {
            System.out.println(str.toUpperCase());
        }
        catch(NullPointerException e) {
            System.out.println("String can be null");
        }
    }
}
```

### try-block

Whenever we write a statement and if the statement is error-prone /
exception prone then we put that code inside the try block.

### catch

The main purpose of catch block is to handle the exception which are
thrown by try block.

**Note:** Catch block is not be executed if there is no exception inside
the try block.

------------------------------------------------------------------------

# 5. try-catch Process

``` java
try {
    Statement 1;
    Statement 2;
    Statement 3;
}
catch(Exception e) {
    Statement 1;
    Statement 2;
}
```

Example:

``` java
class NFE {
    public static void main(String[] args) {

        String str = "10";

        try {
            int a = 10;
            int b = 5;

            System.out.println(a / b);

            int[] arr = {10, 20, 30};

            System.out.println(arr[5]);

            String s = "santanu";

            System.out.println(Integer.parseInt(s));
        }
        catch(NumberFormatException e) {
            System.out.println("String can't be converted into integer");
        }
    }
}
```

------------------------------------------------------------------------

# 6. try-catch-finally

### try

Try is a block that contains risky code.

### catch

It is used to handle exception.

### finally

Finally block is a real time block and the main purpose of finally block
to handle the resources.

------------------------------------------------------------------------

# 7. Flowchart

``` text
              Start
                ↓
         Execute try block
                ↓
            Exception?
           /          \
         YES           NO
          ↓             ↓
 Ignore the rest      Ignore catch
 code in try block       block
          ↓
     Execute catch
          ↓
       finally
```

------------------------------------------------------------------------

# 8. Multiple try-catch block

While working with multiple catch block exception, catch block must be
at the last catch block.

Example:

``` java
class Handling {
    public static void main(String[] args) {

        try {
            int a = 10, b = 5;

            int c = a / b;
            System.out.println(c);

            int[] arr = {10, 20, 30, 40};

            System.out.println(arr[5]);

        }
        catch(ArithmeticException a) {
            System.out.println("can't divide by zero");
        }
        finally {

        }
    }
}
```

------------------------------------------------------------------------

# 9. Multiple catch block

``` java
main() {

    try {
        int a = 10, b = 0;

        int c = a / b;
        System.out.println(c);
    }
    catch(ArithmeticException a) {
        System.out.println("can't divide by zero");
    }

    try {
        int[] arr = {10, 20, 30, 40, 50};

        System.out.println(arr[5]);
    }
    catch(ArrayIndexOutOfBoundsException b) {
        System.out.println("beyond the array limit");
    }
}
```

### Important

While working with multiple catch blocks, child exception class must be
at the last catch block.

Example:

``` java
class MultipleCatch {
    public static void main(String[] args) {

        try {
            int a = 10, b = 0;

            int c = a / b;
            System.out.println(c);

            int[] arr = {10, 20, 30, 40};

            System.out.println(arr[5]);

            String str = "santanu";

            System.out.println(Integer.parseInt(str));
        }
        catch(ArrayIndexOutOfBoundsException e) {
            System.out.println("Array exception");
        }
        catch(ArithmeticException e) {
            System.out.println("Arithmetic exception");
        }
        catch(NumberFormatException e) {
            System.out.println("Number exception");
        }
        catch(Exception e) {
            System.out.println("All type exception");
        }
    }
}
```

------------------------------------------------------------------------

# 10. Nested try block

A try block inside another try block is called nested try block.

Example:

``` java
class NestedTry {
    public static void main(String[] args) {

        try {

            try {
                int a[] = {10, 20, 30};

                System.out.println(a[5]);

            }
            catch(ArrayIndexOutOfBoundsException a) {
                System.out.println(a);
                System.out.println(10);
            }

            catch(ArithmeticException e) {
                System.out.println(e);
            }
        }
    }
}
```

------------------------------------------------------------------------

# 11. Nested catch block

A catch block contains inside another catch block is called nested catch
block.

Example:

``` java
class NestedCatch {
    public static void main(String[] args) {

        try {

            System.out.println(10);

        }
        catch(Exception e) {

            try {

                String a = null;

                System.out.println(a.toLowerCase());

            }
            catch(NullPointerException n) {
                System.out.println("null value can't be converted");
            }

            System.out.println("main method ended");

        }
    }
}
```

------------------------------------------------------------------------

# 12. Nested finally block

Whenever finally block contains inside another finally block is called
nested finally block.

Example:

``` java
class NestedFinally {
    public static void main(String[] args) {

        try {

            String a = "santanu";

            System.out.println(a.toUpperCase());

        }
        catch(Exception e) {
            System.out.println(e);
        }
        finally {

            try {
                System.out.println(10 / 2);
            }
            catch(ArithmeticException a) {
                System.out.println(a);
            }
            finally {
                System.out.println("main method ended");
            }
        }
    }
}
```

------------------------------------------------------------------------

# 13. final vs finally vs finalize

``` text
final
  ↓
variable → final int a = 10
method   → can't override
class    → extends can't use
```

### finally

-   This is try-catch-finally.
-   Used with try-catch.
-   finally block executes whether exception is handled or not.

### finalize()

-   finalize is a method.
-   It is used before the object is removed by GC.
-   If used, it is related to resources for an unused object.

------------------------------------------------------------------------

# 14. final / finally / finalize --- Comparison

  -----------------------------------------------------------------------
  final                   finally                 finalize
  ----------------------- ----------------------- -----------------------
  final is a keyword      finally is a block      finalize is a method

  It is applicable to     It is always executed   If used, it is used
  variable, method,       whether exception is    before object is
  classes                 handled or not          removed

  Variable cannot be      Used with try-catch     Related to
  changed, method cannot                          object/resource cleanup
  be overridden, class                            
  cannot be extended                              
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 15. throw

Throw keyword is used to throw the user defined or customized exception
object.

We can use throw keyword for that purpose.

Example:

``` java
if(age < 18) {

    throw new InvalidException("not eligible for vote");

}
else {

    System.out.println("eligible for vote");

}
```

------------------------------------------------------------------------

# 16. throws

Throws keyword is used when we doesn't want to handle exception and try
to send the exception to the JVM (JVM passes it to other method).

Example:

``` java
class ThrowsDemo {

    public static void main(String[] args) throws InterruptedException {

        for(int i = 1; i <= 5; i++) {

            System.out.println(i);

            Thread.sleep(2000);
        }
    }
}
```

------------------------------------------------------------------------

# 17. throw vs throws

  -----------------------------------------------------------------------
  throw                               throws
  ----------------------------------- -----------------------------------
  throw keyword is used to throw an   throws keyword is used to declare
  exception object explicitly         an exception so caller can handle

  throw keyword always present inside throws keyword always used with
  method body                         method signature

  We can throw only one exception at  We can handle multiple exception
  a time                              using throws keyword

  `throw new ...`                     `throws Exception1, Exception2`

  Throw is followed by an instance    Throws is followed by a class
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 18. Exception vs Error

  -----------------------------------------------------------------------
  Exception                           Error
  ----------------------------------- -----------------------------------
  It is caused by our program         It is caused by other program

  Exceptions are recoverable          Errors are not recoverable

  In Java exceptions are classified   Errors are only checked type in
  as checked and unchecked type       Java
  -----------------------------------------------------------------------

------------------------------------------------------------------------

# 19. Important Topics

``` text
throw and throws program in Java

try-catch vs throws in Java

Exception propagation in Java

Exception vs Error
```

------------------------------------------------------------------------

# Quick Revision

``` text
Exception
   ↓
Unexpected / unwanted situation

try
   ↓
Risky code

catch
   ↓
Handle exception

finally
   ↓
Resource / cleanup block

throw
   ↓
Explicitly throw exception

throws
   ↓
Declare / pass exception
```

