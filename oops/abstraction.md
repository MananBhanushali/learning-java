# Abstraction in Java

An abstract method is a method that is declared without an implementation (without braces, and followed by a semicolon), like this:

```java
abstract void absMethod(); // No Body, only Declaration
```

If a Class includes abstract methods(even one), then the class itself must be declared abstract, as in:

```java
abstract class absClass {
   // declare fields
   // declare nonabstract methods
   abstract void draw();
}
```

**Abstract Classes cannot be instantiated without overriding the Abstract Method, but they can be subclassed**  
**When an Abstract Class is subclassed, the Subclass usually provides implementations for all of the Abstract Methods in its Parent Class. However, if it does not, then the subclass must also be declared abstract.**

```java
abstract class Base {
    abstract void absMethod();
}

class Derived1 extends Base { // Derived Class must Override abstract method or else made abstract
    @Override
    void absMethod() {
        System.out.println("Derived 1 Method");
    }
}

abstract class Derived2 extends Base {
    void someMethod() {
        System.out.println("Derived 2 Method");
    }
}
```