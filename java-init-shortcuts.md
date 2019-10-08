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

## Initialising a set

Rather than
```java
new HashSet<String>() {{
    add("a");
    add("b");
}};
```
instead
```java
Set.of("a", "b");
```