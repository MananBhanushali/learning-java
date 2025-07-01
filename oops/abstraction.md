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

## Interfaces

An Interface is a group of related abstract methods (methods with empty bodies).

Abstract Classes may have non-abstract methods.  
But, **in Interfaces, all Methods are Abstract.**

**Variables can be created in Interfaces, which will be accessible in all the implemented Classes, but they cannot be modified as they are final**

```java
interface Bicycle {
    void applyBrake(int decrement); // will be public always
    void speedUp(int increment);
}

class HeroBicycle implements Bicycle { // implements instead of extends
    int speed = 10;

    @Override
    public void applyBrake(int decrement) { // Methods overriden from Interface should be public
        speed = speed - decrement;
    }

    @Override
    public void speedUp(int increment) {
        speed = speed + increment;
    }

    void blowHorn() { // May or may not be public
        System.out.println("Applying Horn");
    }

}
```

>[!IMPORTANT]
A Class can implement as well as extend.
Multiple Inheritance(extending) is not supported, but **Multiple Implementing is supported in Java**

For Example, a SmartPhone can be thought of as an extended version of a CellPhone, but a SmartPhone is not an extended version of Camera, GPS, Media Player etc, even though it implements their functions and properties.

Hence class SmartPhone can be defined as:
```java
interface Camera {

}

interface GPS {

}

interface MediaPlayer {

}

class CellPhone {

}

class SmartPhone extends CellPhone implements Camera, GPS, MediaPlayer {

}
```

### Default Methods

Interface can have static and default methods.  
Default methods allow us to add new functionality to existing interfaces.  
Classes implementing the interfaces need not implement the default methods.  
Interfaces can also include private methods for default methods to use.

```java
interface Camera {
    void takeSnap(); // static
    void recordVideo(); // static
    private void greet(){ // cannot be used by other classes which implement this interface
        System.out.println("Good Morning");
    }

    default void record4kVideo() {
        greet(); 
        System.out.println("Recording in 4K");
    }
}
```

### Inheritance in Interfaces

An Interface can inherit another interface

```java
interface Base {
    void meth1();
}

interface Derived extends Base { // will inherit meth1()
    void meth2();
}

class MyClass implements Derived {
    public void meth1(){ // Will also have to implement meth1()
        System.out.println("Method 1");
    }
    public void meth2(){
        System.out.println("Method 2");
    }
}

```