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
