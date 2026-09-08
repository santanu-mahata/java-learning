# Java Collections Framework

The Java Collections Framework (JCF) is a set of classes and interfaces
used to store and manage groups of objects.

Main parts:

``` text
List
Set
Queue
Map
```

------------------------------------------------------------------------

# 1. Custom Classes

Collections can store our own custom objects.

``` java
class Person {
    String name;
    int age;

    Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    @Override
    public String toString() {
        return name + " (" + age + ")";
    }
}
```

Example:

``` java
List<Person> people = new ArrayList<>();

people.add(new Person("John", 30));
people.add(new Person("Alice", 25));

System.out.println(people);
```

------------------------------------------------------------------------

# 2. Collections

## a. List

A `List` is an ordered collection.

-   Allows duplicate elements
-   Uses index
-   Maintains insertion order

``` text
List
 |
 ├── ArrayList
 ├── LinkedList
 ├── Stack
 └── Vector
```

## i. ArrayList

``` java
ArrayList<Integer> alist = new ArrayList<>();
```

Another way:

``` java
List<String> names = new ArrayList<>();
```

Here:

``` text
List<String> → stores String type data
names        → variable name
new ArrayList<>() → creates a new ArrayList object
```

### add()

``` java
names.add("Rahul");
names.add("Amit");
names.add("Suman");
```

### List allows duplicates

``` java
names.add("Rahul");
names.add("Suman");
names.add("Rahul");
```

`Rahul` can appear more than once.

### List uses indexes

``` text
Index    Value
  0      Rahul
  1      Amit
  2      Suman
```

Access using `get()`:

``` java
System.out.println(names.get(0));
```

### set()

Used to replace an existing element.

``` java
names.set(1, "John");
```

``` text
[Rahul, Amit, Suman]
          ↓
[Rahul, John, Suman]
```

### remove()

``` java
names.remove("John");
```

### size()

``` java
System.out.println(names.size());
```

### isEmpty()

``` java
System.out.println(names.isEmpty());
```

### contains()

``` java
System.out.println(names.contains("Rahul"));
```

### indexOf()

Returns the index of the first occurrence.

``` java
System.out.println(names.indexOf("Rahul"));
```

### clear()

Removes everything.

``` java
names.clear();
```

------------------------------------------------------------------------

## ii. LinkedList

``` java
LinkedList<Integer> l = new LinkedList<>();
```

LinkedList can be used as a `List` and also as a `Queue`.

Useful methods:

``` java
l.addFirst(10);
l.addLast(20);

l.removeFirst();
l.removeLast();

l.push(30);
l.pop();

l.peek();
```

------------------------------------------------------------------------

## iii. Stack (LIFO)

Stack follows:

``` text
LIFO
Last In First Out
```

Create Stack:

``` java
Stack<Integer> s = new Stack<>();
```

### push()

``` java
s.push(10);
s.push(20);
```

``` text
20 ← top
10
```

### pop()

``` java
System.out.println(s.pop());
```

Output:

``` text
20
```

### peek()

``` java
System.out.println(s.peek());
```

Returns the top element without removing it.

------------------------------------------------------------------------

## iv. Vector

``` java
Vector<Integer> v = new Vector<>();
```

Vector is similar to ArrayList, but its methods are synchronized.

------------------------------------------------------------------------

# 3. Set

A `Set` is a collection that does not allow duplicate elements.

``` text
Set
 |
 ├── HashSet
 └── TreeSet
```

## i. HashSet --- O(1) average

HashSet uses hashing for storage.

Basic operations like `add()` and `remove()` are average O(1).

``` java
HashSet<Integer> hs = new HashSet<>();

hs.add(1);
hs.add(2);
hs.add(1);
hs.add(0);

System.out.println(hs);
```

Duplicate `1` is not stored twice.

**Important:** HashSet does not guarantee sorted order.

For traversal:

``` java
for(Integer num : hs) {
    System.out.println(num);
}
```

------------------------------------------------------------------------

## ii. TreeSet --- O(log n)

TreeSet stores unique elements in sorted order.

``` java
TreeSet<Integer> ts = new TreeSet<>();

ts.add(1);
ts.add(2);
ts.add(1);
ts.add(0);
ts.add(-1);
```

Traversal gives:

``` text
-1
0
1
2
```

TreeSet gives sorted order.

### floor() and ceiling()

``` java
ts.floor(x);
ts.ceiling(x);
```

``` text
floor
→ greatest element <= x

ceiling
→ smallest element >= x
```

------------------------------------------------------------------------

# 4. Queue (FIFO)

Queue follows:

``` text
FIFO
First In First Out
```

Elements are processed in the order they are added.

------------------------------------------------------------------------

## i. ArrayDeque

Java does not have a class called `ArrayQueue`.

For queue/deque operations, `ArrayDeque` can be used.

``` java
ArrayDeque<Integer> ad = new ArrayDeque<>();

ad.offer(2);
ad.offer(6);
ad.offer(9);
ad.offer(10);
```

### peek()

``` java
System.out.println(ad.peek());
```

Output:

``` text
2
```

### poll()

``` java
ad.poll();
System.out.println(ad.peek());
```

Output:

``` text
6
```

Useful methods:

``` text
offer()
peek()
poll()
offerFirst()
offerLast()
```

------------------------------------------------------------------------

## ii. LinkedList as Queue

LinkedList implements both `List` and `Queue`.

``` java
Queue<String> queue = new LinkedList<>();

queue.add("First");
queue.add("Second");

System.out.println(queue.poll());
```

Output:

``` text
First
```

------------------------------------------------------------------------

## iii. PriorityQueue (Min Heap)

PriorityQueue processes elements according to priority.

By default, it behaves like a min-heap for natural ordering.

``` java
PriorityQueue<Integer> pq = new PriorityQueue<>();

pq.offer(1);
pq.offer(5);
pq.offer(0);
pq.offer(4);

System.out.println(pq.peek());
```

Output:

``` text
0
```

The smallest element is returned first.

``` java
System.out.println(pq.poll());
```

removes the current highest-priority element.

------------------------------------------------------------------------

# 5. Map

A `Map` stores data in:

``` text
key → value
```

Important:

``` text
Key must be unique
Value can be duplicate
Map does not use index like ArrayList
```

Example:

``` java
HashMap<Integer, String> mp = new HashMap<>();

mp.put(1, "Santanu");
mp.put(2, "Vikash");
mp.put(3, "Rima");

System.out.println(mp);
```

------------------------------------------------------------------------

## i. HashMap

HashMap is an implementation of the `Map` interface that uses hashing.

### put()

``` java
mp.put(1, "Santanu");
mp.put(2, "Vikash");
mp.put(3, "Rima");
```

If the same key is inserted again, its value is replaced.

``` java
mp.put(1, "Rahul");
```

Now key `1` points to `Rahul`.

### keySet()

Returns all keys as a Set.

``` java
Set<Integer> st = mp.keySet();

System.out.println(st);
```

------------------------------------------------------------------------

## ii. TreeMap

TreeMap stores entries in sorted order of keys.

``` java
TreeMap<Integer, String> mp = new TreeMap<>();

mp.put(3, "Rima");
mp.put(1, "Santanu");
mp.put(2, "Vikash");
```

Keys:

``` text
1
2
3
```

------------------------------------------------------------------------

# 6. Iterator

Iterator is used to traverse through a collection.

``` java
Iterator<Integer> it = collection.iterator();

while(it.hasNext()) {
    System.out.println(it.next());
}
```

### hasNext()

Checks whether another element is available.

### next()

Returns the next element.

------------------------------------------------------------------------

# 7. ListIterator

ListIterator is a special iterator for `List`.

It can move in both directions.

``` java
List<String> list = new ArrayList<>();

list.add("One");
list.add("Two");

ListIterator<String> iterator = list.listIterator();

while(iterator.hasNext()) {
    System.out.println(iterator.next());
}
```

Backward:

``` java
while(iterator.hasPrevious()) {
    System.out.println(iterator.previous());
}
```

``` text
Iterator
   ↓
Forward

ListIterator
   ↓
Forward + Backward
```

------------------------------------------------------------------------

# 8. Custom Comparator

Comparator is used when we want our own sorting logic.

Example: sort `Person` according to age.

``` java
Collections.sort(people, new Comparator<Person>() {

    @Override
    public int compare(Person p1, Person p2) {
        return p1.age - p2.age;
    }
});
```

Comparator is useful when default/natural ordering is not what we want.

------------------------------------------------------------------------

# 9. Common Algorithms / Utility Methods

## Collections.sort()

``` java
List<Integer> list = new ArrayList<>();

list.add(3);
list.add(1);
list.add(2);

Collections.sort(list);

System.out.println(list);
```

Output:

``` text
[1, 2, 3]
```

## Collections.max()

``` java
int max = Collections.max(list);
System.out.println(max);
```

Output:

``` text
3
```

## Collections.min()

``` java
int min = Collections.min(list);
System.out.println(min);
```

Output:

``` text
1
```

## Collections.reverse()

``` java
Collections.reverse(list);
System.out.println(list);
```

Output:

``` text
[3, 2, 1]
```

## Arrays.sort()

``` java
int[] array = {3, 1, 2};

Arrays.sort(array);

System.out.println(Arrays.toString(array));
```

Output:

``` text
[1, 2, 3]
```

## Collections.frequency()

Returns how many times an element occurs.

``` java
int frequency = Collections.frequency(list, 2);
System.out.println(frequency);
```

## Collections.binarySearch()

Searches for an element using binary search.

**The list must be sorted first.**

``` java
Collections.sort(list);

int index = Collections.binarySearch(list, 2);

System.out.println(index);
```

For:

``` text
[1, 2, 3]
```

Output:

``` text
1
```

## Math.pow()

``` java
double result = Math.pow(2, 3);

System.out.println(result);
```

Output:

``` text
8.0
```

------------------------------------------------------------------------

# 10. Quick Comparison

  Collection      Duplicate     Order                 Index   Main Idea
  --------------- ------------- --------------------- ------- ----------------------
  ArrayList       Yes           Insertion order       Yes     Fast access
  LinkedList      Yes           Insertion order       Yes     List + Queue
  Stack           Yes           LIFO                  Yes     push / pop
  Vector          Yes           Insertion order       Yes     Synchronized list
  HashSet         No            No guaranteed order   No      Unique elements
  TreeSet         No            Sorted                No      Unique + sorted
  ArrayDeque      Yes           Queue/Deque order     No      Fast queue/deque
  PriorityQueue   Yes           Priority order        No      Priority based
  HashMap         Keys unique   No guaranteed order   No      Key → Value
  TreeMap         Keys unique   Sorted by key         No      Key → Value + sorted

------------------------------------------------------------------------

# Quick Revision

``` text
List
 ↓
Ordered
Duplicates allowed
Index available

Set
 ↓
Duplicates not allowed

Queue
 ↓
FIFO

Stack
 ↓
LIFO

Map
 ↓
Key → Value
Key must be unique
```

### Remember

``` text
ArrayList
→ List + index + duplicates

LinkedList
→ List + Queue

Stack
→ LIFO

HashSet
→ Unique + no guaranteed order

TreeSet
→ Unique + sorted

ArrayDeque
→ Queue / Deque

PriorityQueue
→ Priority based

HashMap
→ Key → Value

TreeMap
→ Key → Value + sorted keys

Iterator
→ Traverse collection

ListIterator
→ Forward + backward

Comparator
→ Custom sorting
```

------------------------------------------------------------------------

# Java Collections Learning Flow

``` text
Java Collections Framework
          ↓
        List
          ↓
ArrayList → LinkedList → Stack → Vector
          ↓
         Set
          ↓
HashSet → TreeSet
          ↓
        Queue
          ↓
ArrayDeque → LinkedList → PriorityQueue
          ↓
         Map
          ↓
HashMap → TreeMap
          ↓
      Iterator
          ↓
   ListIterator
          ↓
     Comparator
          ↓
 Collections / Arrays utilities
```

