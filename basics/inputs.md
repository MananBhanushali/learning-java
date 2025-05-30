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