# Java data structures

## Default values

* byte, short, int: `0`
* long: `0L`
* float: `0.0f`
* double: `0.0d`
* char: `'\u0000'` - the null character not `null`
* object (inc. String): `null`
* boolean: `false`

## Arrays

### Initialisation and accessing elements

Stores a fixed number of values of a single type in a continuous memory location.
Default initialisation using default values above.
Elements are accessed using the standard square brackets notation.

```java
int[] testArray = new int[4];
System.out.println(Arrays.toString(testArray));
// [0, 0, 0, 0]
testArray[0] = 0;
testArray[1] = 1;
testArray[2] = 1;
testArray[3] = 2;
System.out.println(Arrays.toString(testArray));
// [0, 1, 1, 2]
int[] secondTest = new int[5] {1, 1, 2, 3, 5};
System.out.println(testArray[3]);
// 2
System.out.println(secondTest[1]);
// 1
```

### Standard library functions for arrays

The `System` class provides a copy method that copies a specified number `length` of elements from a starting position `srcPos` of a source array `src` to a destination array `dest` beginning at the destination position `destPos`.

```java
System.arraycopy(   Object src, int srcPos,
                    Object dest, int destPos, int length);
```

The `java.util.Arrays` class contains other useful methods for instance:-
* `binarySearch`: binary search on a sorted array. (No guarantee which value is found.)
* `equals`: compares two arrays to see if they are equal.
* `sort` and `parallelSort` for sorting
* `fill` assigns multiple contiguous values at once

## Stacks

Use `java.util.Stack`.

* Last-in is first-out.
* Dynamic data structures without fixed size or memory allocation.

```java
import java.util.Stack;
Stack<String> stk = new Stack<>();
System.out.println(stk.empty());
// true
stk.push("0");
System.out.println(stk.empty());
// false
stk.push("hi");
stk.push("fifty");
String top = stk.pop();
System.out.println(top);
// fifty
String just_looking = stk.peek();
System.out.println(just_looking);
// hi
String now_popping = stk.pop();
System.out.println(now_popping);
// hi
```
The `.empty()` method tells us if the stack is empty.
The `.peek()` method gets the top element without removing it.