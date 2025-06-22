# Methods in Java

A Function inside a Class is called a Method

```java
<datatype> name(parameters){ 
    code
    return  // To return nothing, use void datatype
}
```
Parameters are variables defined in the function definition, acting as placeholders for the values that will be passed in. Arguments are the actual values passed to the function when it's called

---
A Method can be called by creating an Object of the Class of which the Method is a part of

```java
Calculator obj = new Calculator; // Creating Object
obj.sum(a, b); // Calling Method
```
---

The values from the method call (a and b) are copied to the method/function. **Hence even if we modify their values inside the method, their value outside the method does not change.**

```java
public class Main {
    public static void main(String[] args){
        int x = 45;
        change(x);
        System.out.println(x); // Will print 45
    }

    static void change(int x){
        x = 98;
    }
}
```

>[!IMPORTANT]
**Incase of array( or any Objects ), a reference of the array is passed (not a copy). Hence, an Object can be modified by a method**

```java
public class Main {
    public static void main(String[] args){
        int []xArray = {1, 2, 4, 8 , 16};
        change(xArray);
        System.out.println(xArray[0]); // Will print 98
    }

    static void change(int[] x){
        x[0] = 98;
    }
}
```

---

**Static keyword is used to associate a Method of a given Class with the Class rather than the Object. Static method in a Class is shared by all the Objects. Hence the method can be called directly without creating an Object**

```java

public class Main {
    public static void main(String[] args){
        Calculator.sum(1, 4); // For Static

        Calculator obj = new Calculator();
        obj.subtract(2, 1); // For Non-Static
    }
}

class Calculator {
    static int sum(int a, int b){
        return a+b;
    }

    int subtract(int a, int b){
        return a-b;
    }
}
```

## Method Overloading

Method Overloading can be performed by giving the same name to two Methods with different parameters.
Method Overloading cannot be performed by given the same name to two Methods with different datatypes.

```java
int foo(){
    return 100;
}

int foo(int x){ // Valid
    return x;
}

void foo(){ // Not Valid
    system.out.println("Void");
}

void foo(int x, int y){ // Valid
    system.out.println(x + y);
}
```

## Variable Arguments ( VarArgs )

Used when a Method needs to have Indefinite Number of Arguments

```java
public class Main {
    public static void main(String[] args){
        System.out.println(test(1, 2, 4));
    }

    static int test(int a , int b, int ... extraArgsArray){ // Minimum Two Arguments required
        int sum = a + b;
        for (int i:extraArgsArray){
            sum += i;
        }
        return sum;
    }
}
```

## Recursion

Calling of a function by itself is called Recursion
( for ex: n factorial = n * n-1 factorial )

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