# Inputs in Java

```java
package com.company;
import java.util.Scanner;

public class Main {
    public static void main(String[] args){
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter input");
        String input = sc.nextLine();
        System.out.println(input);
    }
}

```

- sc.next() will take only first word of input
- sc.nextLine() will take whole input