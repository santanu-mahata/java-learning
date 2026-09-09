# File Handling

File handling defines how we can read and write data on a file. Java io package contains all the classes through which we can perform all input and output operations in the file.

## Stream

Stream is a sequence of data or the basis of java.io package. all the classes divided into two stream.

```text
                    Stream
                   /      \
                Byte     character
```

## File handling methods

1. `canRead()`
2. `canWrite()`
3. `createNewFile()`
4. `delete()`
5. `exists()`
6. `length()`
7. `getName()`
8. `getAbsolutePath()`
9. `mkdir()`
10. `list()`
11. `read()`
12. `write()`
13. `renameTo()`

## File handling classes

1. File
2. FileReader
3. FileWriter
4. FileInputStream
5. FileOutputStream
6. BufferedInputStream
7. BufferedOutputStream

## operations of file

1. create file
2. get file information
3. read
4. write

---

## Create File

```java
import java.io.*;

class createfile {
    public static void main(String[] args) {

        File f = new File("D:\\java\\file-handling\\co.txt");

        try {
            if (f.createNewFile()) {
                System.out.println("file created !!");
            }
            else {
                System.out.println("file already exists");
            }
        }
        catch (IOException e) {
            System.out.println("exception handling");
        }
    }
}
```

→ File created !!

when we create the file we need to handle the exception also. we can also process to handle the exception.

---

## A java program to display the file info

```java
class fileInfo {
    public static void main(String[] args) {

        File f = new File("D:\\java\\file-handling\\co.txt");

        if (f.exists()) {
            System.out.println("file name: " + f.getName());
            System.out.println("File location: " + f.getAbsolutePath());
            System.out.println("File writable: " + f.canWrite());
            System.out.println("File Readable: " + f.canRead());
        }
        else {
            System.out.println("File doesn't exist");
        }
    }
}
```

---

## Write into a file

```java
import java.io.*;

class fileWriter {
    public static void main(String[] args) {

        try {
            FileWriter f = new FileWriter("D:\\java\\file-handling\\co.txt");

            try {
                f.write("java programming");
            }
            finally {
                f.close();
            }

            System.out.println("successfully data write in file");
        }
        catch (IOException e) {
            System.out.println();
        }
    }
}
```

→ successfully data write in file.

---

## Read data from a file

```java
class fileReader {
    public static void main(String[] args) {

        try {

            FileReader fr = new FileReader("D:\\java\\file-handling\\co.txt");

            try {
                int i;
                while ((i = fr.read()) != -1) {
                    System.out.println((char) i);
                }
            }
            finally {
                fr.close();
            }
        }
        catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

→ java programming in is the best!!

---

## Rename a file

```java
class renameFile {
    public static void main(String[] args) {

        File f = new File("D:\\java\\file-handling\\co.txt");
        File f2 = new File("D:\\java\\file-handling\\co2.txt");

        if (f.exists()) {
            System.out.println(f.renameTo(f2));
        }
        else {
            System.out.println("file doesn't exist..!!");
        }
    }
}
```

→ true

---

## Copy one file data to another

```java
class copyFile {
    public static void main(String[] args) {

        FileInputStream r = new FileInputStream(path);
        FileOutputStream w = new FileOutputStream(path);

        int i;

        while ((i = r.read()) != -1) {
            w.write((char) i);
        }

        System.out.println("data copy successfully");
    }
}
```

```java
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;
```

