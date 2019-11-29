# Java common tasks

## Parsing and reading

The class `java.util.Scanner` provides a iterator-like methods to parse input.

For console input:

```java
Scanner scanner = new Scanner(System.in);
int i = scanner.nextInt();
```

For file input:
```java
Scanner scanner = new Scanner(new File("myNumbers"));
long nextLong = scanner.nextLong();
```