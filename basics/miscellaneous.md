# Miscellaneous

## Factorial of a Number

1. Using Incrementing For Loop
```java
static int factorial(int n){
    int result = 1;

    for (int i = 1; i <= n; i++) {
        result *= i;
    }
    
    return result;
}
```
2. Using Decrementing For Loop
```java
static int factorial(int n) {
    int result = 1;

    for (int i = n; i > 1; i--) {

        if (i == 0) {
            result = 1;
        } else {
            result *= i;
        }
    }
    return result;
}
```

3. Using Recursion
```java
int factorial(int n){
    if (n==0 || n==1){
        return 1;
    }
    else {
        return n*factorial(n-1);
    }
}
```

## Fibonacci Series

The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones, typically starting with 0 and 1. ( 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, and so on ).  
It is defined by the recursive formula:  

**F(n) = F(n-1) + F(n-2), with F(0) = 0 and F(1) = 1**

```java
public class Main {
    public static void main(String[] args) {

        for (int i = 1; i <= 5; i++) { // Will Print first 5 terms
            System.out.println(fibonacci(i));
        }
    }

    static int fibonacci(int n) { // Gives nth term of Fibonacci Series
        int result = 0;
        if (n == 0 || n==1) {}
        else if (n == 2) {
            result = 1;
        }
        else {
            result = fibonacci(n-1) + fibonacci(n-2);
        }

        return result;
    }
}
```


## Generate Random Numbers 

```java
import java.util.Randoom;

public class Main{
    public static void main(String[] args){
        Random random = new Random();
        num = random.nextInt(<max> + 1)
    }
}
```
