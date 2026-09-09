# Java File Handling — Additional Notes

These are the topics that were not covered in the basic File Handling notes.

---

## 1. BufferedReader

`BufferedReader` is used to read character data efficiently.

It reads text using a buffer, so it is generally more efficient than reading one character at a time with `FileReader`.

### Example

```java
import java.io.*;

class BufferedReaderExample {
    public static void main(String[] args) {

        try {
            BufferedReader br =
                    new BufferedReader(new FileReader("D:\\java\\file-handling\\co.txt"));

            String line;

            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }

            br.close();

        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

### Important method

```java
readLine()
```

`readLine()` reads one complete line at a time.

---

## 2. BufferedWriter

`BufferedWriter` is used to write character data efficiently.

It uses a buffer while writing data.

### Example

```java
import java.io.*;

class BufferedWriterExample {
    public static void main(String[] args) {

        try {
            BufferedWriter bw =
                    new BufferedWriter(new FileWriter("D:\\java\\file-handling\\co.txt"));

            bw.write("Java Programming");
            bw.newLine();
            bw.write("File Handling");

            bw.close();

        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

### Important method

```java
newLine()
```

Used to write a new line.

---

## 3. BufferedInputStream

`BufferedInputStream` is used to read **byte data** efficiently.

It works with an `InputStream`.

### Example

```java
import java.io.*;

class BufferedInputStreamExample {
    public static void main(String[] args) {

        try {
            BufferedInputStream bis =
                    new BufferedInputStream(
                            new FileInputStream("D:\\java\\file-handling\\co.txt"));

            int i;

            while ((i = bis.read()) != -1) {
                System.out.print((char) i);
            }

            bis.close();

        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

---

## 4. BufferedOutputStream

`BufferedOutputStream` is used to write **byte data** efficiently.

It works with an `OutputStream`.

### Example

```java
import java.io.*;

class BufferedOutputStreamExample {
    public static void main(String[] args) {

        try {
            BufferedOutputStream bos =
                    new BufferedOutputStream(
                            new FileOutputStream("D:\\java\\file-handling\\co.txt"));

            String data = "Java Programming";

            bos.write(data.getBytes());

            bos.close();

        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

---

## 5. PrintWriter

`PrintWriter` is used to write formatted text to a file or other character-output destination.

### Example

```java
import java.io.*;

class PrintWriterExample {
    public static void main(String[] args) {

        try {
            PrintWriter pw =
                    new PrintWriter("D:\\java\\file-handling\\co.txt");

            pw.println("Java Programming");
            pw.println("File Handling");

            pw.close();

        } catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

### Important methods

```java
print()
println()
printf()
```

---

## 6. Scanner with Files

`Scanner` can also be used to read data from a file.

### Example

```java
import java.io.*;
import java.util.*;

class ScannerFileExample {
    public static void main(String[] args) {

        try {
            Scanner sc =
                    new Scanner(new File("D:\\java\\file-handling\\co.txt"));

            while (sc.hasNextLine()) {
                System.out.println(sc.nextLine());
            }

            sc.close();

        } catch (FileNotFoundException e) {
            System.out.println(e);
        }
    }
}
```

### Important methods

```java
hasNextLine()
nextLine()
```

---

# 7. Path

`Path` represents the location/path of a file or directory.

It belongs to:

```java
java.nio.file.Path
```

### Example

```java
import java.nio.file.*;

class PathExample {
    public static void main(String[] args) {

        Path path = Paths.get("D:\\java\\file-handling\\co.txt");

        System.out.println(path);
    }
}
```

---

# 8. Paths

`Paths` is a utility class used to create a `Path` object.

### Example

```java
Path path = Paths.get("D:\\java\\file-handling\\co.txt");
```

Here:

```text
Paths
  ↓
creates
  ↓
Path
```

---

# 9. Files

`Files` is a utility class from `java.nio.file` used for file and directory operations.

It provides methods for:

```text
create
read
write
copy
move
delete
check
```

### Example

```java
import java.nio.file.*;

class FilesExample {
    public static void main(String[] args) {

        try {
            Path path = Paths.get("D:\\java\\file-handling\\co.txt");

            Files.writeString(path, "Java Programming");

            String data = Files.readString(path);

            System.out.println(data);

        } catch (Exception e) {
            System.out.println(e);
        }
    }
}
```

---

# 10. NIO.2

NIO.2 is the modern Java file-system API introduced in **Java 7**.

It is mainly based on:

```text
Path
Paths
Files
```

It provides a more powerful and convenient way to work with files and directories.

### Basic structure

```text
java.nio.file
      │
      ├── Path
      ├── Paths
      └── Files
```

---

# 11. Serialization

Serialization means converting an object's state into a byte stream so that the object can be stored or transferred.

```text
Object
   ↓
Serialization
   ↓
Byte Stream
```

A class generally implements:

```java
Serializable
```

### Example

```java
import java.io.*;

class Student implements Serializable {

    int id;
    String name;

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }
}
```

### Writing an object

```java
ObjectOutputStream oos =
        new ObjectOutputStream(
                new FileOutputStream("student.txt"));

Student s = new Student(101, "Santanu");

oos.writeObject(s);

oos.close();
```

---

# 12. Deserialization

Deserialization means converting the byte stream back into an object.

```text
Byte Stream
    ↓
Deserialization
    ↓
Object
```

### Example

```java
ObjectInputStream ois =
        new ObjectInputStream(
                new FileInputStream("student.txt"));

Student s = (Student) ois.readObject();

System.out.println(s.id);
System.out.println(s.name);

ois.close();
```

---

# Quick Revision

| Topic | Main Purpose |
|---|---|
| `BufferedReader` | Efficiently read character/text data |
| `BufferedWriter` | Efficiently write character/text data |
| `BufferedInputStream` | Efficiently read byte data |
| `BufferedOutputStream` | Efficiently write byte data |
| `PrintWriter` | Write formatted text |
| `Scanner` with File | Read file data easily |
| `Path` | Represents a file/directory path |
| `Paths` | Creates `Path` objects |
| `Files` | File/directory operations |
| `NIO.2` | Modern Java file-system API |
| Serialization | Object → byte stream |
| Deserialization | Byte stream → object |

---

# File Handling Learning Order

```text
File
 ↓
FileReader / FileWriter
 ↓
FileInputStream / FileOutputStream
 ↓
BufferedReader / BufferedWriter
 ↓
BufferedInputStream / BufferedOutputStream
 ↓
PrintWriter / Scanner
 ↓
Path / Paths / Files
 ↓
NIO.2
 ↓
Serialization / Deserialization
```

## Final Note

For basic Java File Handling, the earlier notes + these topics give a much more complete foundation.

For Java backend development, you do not need to memorize every method. Understand **what each class is used for** and practice writing a few programs.

