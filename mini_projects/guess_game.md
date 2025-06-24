# Guess Game in Java

Created a Guess Game while learning about Classes and Methods

```java
package com.company;

import java.util.Scanner;
import java.util.Random;

public class Main {
    public static void main(String[] args) {
        GuessGame game = new GuessGame();

        while (true) {
            game.start();
        }
    }
}

class GuessGame {
    void start() {
        // Find use of Final
        int userGen = userGuess();
        int compGen = computerGuess();

        if (checkGuess(userGen, compGen)) {
            System.out.println("Correct Guess");
            System.exit(0);
        } else {
            System.out.printf("Incorrect Guess.Computer Guess was %s. Try Again\n", compGen);
        }
    }

    int userGuess() {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter your Guess from 1-9: ");
        int input = sc.nextInt();
        return input;
    }

    int computerGuess() {
        Random random = new Random();
        int randInt = random.nextInt(1, 10);
        return randInt;
    }

    boolean checkGuess(int userGen, int compGen) {
        return userGen == compGen;
    }

}

```