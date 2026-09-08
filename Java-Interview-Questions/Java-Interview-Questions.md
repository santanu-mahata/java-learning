# ☕ Java Interview Questions

-   **Java Basics** → Questions 1--75
-   **Java Intermediate** → Questions 76--178
-   **Java Advanced** → Questions 179--196

------------------------------------------------------------------------

# 🟢 Java Basics

## Java Fundamentals

1.  Is Java platform independent? If then how?
2.  What are the top two features of Java?
3.  What is JVM, JIT?
4.  What are memory managers available with JVM?
5.  What is a classloader?
6.  Difference between JVM, JRE and JDK.
7.  What are different C-type modifiers in Java?
8.  Explain `public static void main(String args[])` in Java.
9.  What is Java String Pool?
10. What will happen if we declare `final` before the main method?
11. What are packages in Java?
12. Why packages are used?
13. What are the advantages of packages in Java?
14. How many types of packages are there in Java?
15. Explain different data types in Java.
16. When is byte datatype used?
17. Can we declare pointers in Java?
18. What is the default value of byte datatype in Java?
19. What is the default value of float and double datatype in Java?
20. What is the wrapper class in Java?
21. Why do we need wrapper classes?
22. Difference between instance and local variables.
23. What are the default values assigned to variables and instance in
    Java?
24. What is a class variable?
25. What is the default value stored in local variables?
26. Explain the difference between instance variable and class variable.
27. What is a static variable?
28. What is the difference between `System.out`, `System.err` and
    `System.in`?
29. What do you understand by an I/O stream?
30. What is the difference between the Reader/Writer classes hierarchy
    and the InputStream/OutputStream class hierarchy?
31. What are the super most classes for all streams?
32. What are the FileInputStream and FileOutputStream streams?

------------------------------------------------------------------------

## Input / Output and Operators

33. What is the purpose of using BufferedInputStream and
    BufferedOutputStream classes?
34. What are FileStreams?
35. What is an I/O filter?
36. How many ways can we take input from the console?
37. Difference in the use of `print`, `println` and `printf`.
38. What are operators?
39. How many types of operators are available in Java?
40. Explain the difference between `>>` and `>>>` operator.
41. Which Java operator is right associative?
42. What is a ternary operator?
43. What is covariant return type?
44. What is the transient keyword?
45. Difference between the methods `sleep()` and `wait()`.
46. Differences between String and StringBuffer.
47. What is the difference between StringBuffer and StringBuilder?
48. Which among StringBuilder or StringBuffer should be preferred when
    there are a lot of updates occurring to the data?
49. Why is StringBuffer called mutable?
50. How is the creation of a String using `new` different from a String
    literal?

------------------------------------------------------------------------

## Arrays and OOP Basics

51. What is an array in Java?
52. On which memory area are arrays created in Java?
53. What are the types of an array?
54. Why does the Java array index start with 0?
55. What is the difference between `==` in array and `equals()` array?
56. How to copy an array in Java?
57. What do you understand by the jagged array?
58. Is it possible to have an array volatile?
59. What are the advantages and disadvantages of an array?
60. What is an object-oriented paradigm?
61. What are the main concepts of OOPs in Java?
62. What is the difference between an object-oriented programming
    language and an object-based programming language?
63. How is the `new` operator different from the `newInstance()`
    operation in Java?
64. What are classes in Java?
65. What is the difference between static (class) method and instance
    method?
66. What is this keyword in Java?
67. What are access specifiers and types of access specifiers?
68. What will be the initial value of an object reference which is
    defined as an instance variable?
69. What is an object?
70. What are the different ways to create objects?
71. What are the advantages and disadvantages of object cloning?
72. What are the advantages of passing `this` into a method instead of
    the current class object itself?
73. What is a constructor?
74. What happens if you don't provide a constructor in a class?
75. How many types of constructors are used in Java?

------------------------------------------------------------------------

# 🟡 Java Intermediate

## OOP and Constructors

76. What is the purpose of using a default constructor?
77. What do you understand by copy constructor in Java?
78. Where and how can you use a private constructor?
79. What are the differences between the constructor and methods?
80. What is an interface?
81. Give some features of the interface.
82. What is a marker interface?
83. What are the differences between abstract class and interface?
84. What do you mean by data encapsulation?
85. What are the advantages of encapsulation in Java?
86. What is the primary benefit of encapsulation?
87. What do you mean by aggregation?
88. What is the "is-a" relationship in OOPs Java?
89. Define inheritance.
90. What are the different types of inheritance in Java?
91. What is multiple inheritance? Is it supported by Java?
92. How is inheritance in C++ different from Java?
93. How is the `new` operator different from the `newInstance()`
    operation in Java?
94. What are classes in Java?
95. What is the difference between static (class) method and instance
    method?
96. What is this keyword in Java?
97. What are access specifiers and types of access specifiers?
98. What will be the initial value of an object reference which is
    defined as an instance variable?
99. What is an object?
100. What are the different ways to create objects?
101. What are the advantages and disadvantages of object cloning?
102. What are the advantages of passing `this` into a method instead of
     the current class object itself?
103. What is a constructor?
104. What happens if you don't provide a constructor in a class?
105. How many types of constructors are used in Java?

------------------------------------------------------------------------

## Inheritance and Polymorphism

106. What is the difference between inheritance and composition?
107. What is aggregation?
108. What is composition in Java?
109. State the difference between Composition and Aggregation.
110. Can the constructor be inherited?
111. What is polymorphism?
112. What is runtime polymorphism or dynamic method dispatch?
113. What is method overriding?
114. What is method overloading?
115. Can we override the static method?
116. Can we overload the overridden method?
117. Can we overload the main method?
118. What are method overloading and method overriding?
119. Can we override the private methods?
120. Can we change the scope of the overridden method?
121. Can we modify the throws clause of the superclass method while
     overriding it in the subclass?
122. Can you have virtual functions in Java?
123. What is abstraction?
124. What is abstract class?
125. When abstract methods are used?
126. How can you achieve serialization in the child class if the base
     class is implementing the Serializable interface?
127. What is Collection Framework in Java?
128. Explain various interfaces used in the Collection Framework.
129. How can you synchronize an ArrayList in Java?
130. Why do we need a synchronized ArrayList when we have vectors (which
     are synchronized) in Java?
131. Why can't we create a generic array?
132. Can we store homogeneous elements in ArrayList? Explain.
133. Explain the method to convert ArrayList to Array and Array to
     ArrayList.

------------------------------------------------------------------------

## Collections

134. How does the size of ArrayList grow dynamically and also state how
     it is implemented internally?
135. What is a Vector in Java?
136. How to make Java ArrayList read-only?
137. What is a priority queue in Java?
138. Explain the LinkedList class.
139. What is the Stack class in Java and what are the various methods
     provided by it?
140. What is Set in the Java Collections Framework and List under which
     implementations?
141. What is the HashSet class in Java and how does it store elements?
142. What is LinkedHashSet in Java Collections Framework?
143. What is a Map interface?
144. Explain TreeMap in Java.
145. What is EnumSet?
146. What is BlockingQueue?
147. What is the ConcurrentHashMap in Java and how do you implement it?
148. Can you use arrays as a Map key?
149. What is an Iterator?
150. What is an Enumeration?
151. What is the difference between Collection and Collections?
152. Differentiate between Array and ArrayList in Java.
153. What is the difference between Array and Collection in Java?
154. Difference between ArrayList and LinkedList.
155. Difference between ArrayList and Vector in Java?
156. What is the difference between Iterator and Enumeration?
157. Differentiate between HashMap and HashTable.
158. Differentiate between Iterator and Enumeration.
159. What is the difference between Comparable and Comparator?
160. What is the difference between Set and Map?

------------------------------------------------------------------------

# 🟠 Java Intermediate --- Multithreading & Exception Handling

161. What do you understand by object cloning and how do you achieve it
     in Java?
162. How do exceptions affect the program if it is not handled?
163. What is the use of the final keyword?
164. What purpose do the keywords `final`, `finally` and `finalize`
     fulfill?
165. What is the difference between `this()` and `super()` in Java?
166. What is multithreading?
167. What do you mean by a multi-threaded program?
168. What are the advantages of multithreading?
169. What are the different ways in which a Thread can be created?
170. What is a Thread?
171. Differentiate between process and thread.
172. Describe the life cycle of a thread.
173. Explain various methods under the Thread class.
174. Explain the main thread under Thread class.
175. Explain the main thread under Thread class and its execution.
176. What is a daemon thread?
177. What are the ways in which a thread can enter the waiting state?
178. How does multi-threading take place on a computer with a single
     CPU?

------------------------------------------------------------------------

# 🔴 Java Advanced

## Multithreading, Garbage Collection, Regex & JDBC

179. Explain the `fail-fast` iterator and `fail-safe` iterator along
     with examples for each.
180. What is Exception Handling?
181. How many types of exceptions can occur in a Java program?
182. Difference between an Error and Exception.
183. Explain the hierarchy of Java Exception classes.
184. Explain Runtime Exceptions.
185. What is NullPointerException?
186. When is the NullPointerException thrown?
187. What is the difference between Checked Exception and Unchecked
     Exception?
188. What is the base class for Errors and Exceptions?
189. Is it necessary that each try block must be followed by a catch
     block?
190. What is exception propagation?
191. What will happen if you put `System.exit(0)` on the try or catch
     block? Will finally block execute?

------------------------------------------------------------------------

## Advanced Java Concepts

192. What are the different types of thread priorities in Java? And what
     is the default priority of a thread assigned by JVM?
193. Why is Garbage Collection necessary in Java?
194. What is the drawback of Garbage Collector?
195. Explain the difference between a minor garbage collection and full
     garbage collection.
196. How will you identify major and minor garbage collections in Java?

------------------------------------------------------------------------

# 📌 Topics Covered

``` text
Java Basics
    ↓
JVM / JDK / JRE
    ↓
Data Types & Variables
    ↓
Operators
    ↓
Input / Output
    ↓
String
    ↓
Arrays
    ↓
OOP
    ↓
Constructors
    ↓
Inheritance
    ↓
Polymorphism
    ↓
Abstraction & Interface
    ↓
Encapsulation
    ↓
Collections
    ↓
Multithreading
    ↓
Exception Handling
    ↓
Garbage Collection
    ↓
Advanced Java
```

------------------------------------------------------------------------

## 🎯 Practice Strategy

Don't try to memorize all the questions at once.

Follow the numbering:

**1--75 → Java Basics**

**76--178 → Java Intermediate**

**179--196 → Java Advanced**

Understand each question first, then write small Java programs wherever
possible.

