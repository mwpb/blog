# Java initialisation shortcuts

In Java some of the standard constructors can be a little unwieldy.
This is especially the case when trying to inline some kind of condition.
On this page I am collecting initialisation shortcuts that I have found useful.
The purpose is to make the code more readable and performance has not been considered.

At the moment they all require:

```java
import java.util.*;
```

## Initialising an array of characters

Rather than
```java
new char[] {'A', 'C', 'G', 'T'};
```
instead:
```java
"ACGT".toCharArray();
```

## Initialising a list

Rather than any of:
```java
List<String> supplierNames1 = new ArrayList<String>();
List<String> supplierNames2 = new LinkedList<String>();
List<String> supplierNames3 = new Vector<String>();
```
instead
```java
List.of();
```

## Initialising a set

Rather than
```java
Set<String>s = new HashSet<String>();
set.add("a"); 
set.add("b");
```
instead
```java
Set.of("a", "b");
```