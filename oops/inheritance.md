# Inheritance in Java

Inheritance means deriving new things from existing things.  
**Derived Class( subclass ) inherits all (not private) properties (methods, variables) from its Base Class( superclass ).**

```java
class Base {
    printBase() {
        System.out.println("This is a whoAreYou of the Base Class");
    }
}

class Derived extends Base { // Derived Class will also inherit printBase whoAreYou from Base Class
    printDerived() {
        System.out.println("This is a whoAreYou of the Derived Class");
    }
}
```
>[!NOTE]
Java Doesn't support Multiple Inheritance, i.e. a Derived Class cannot have two Base Classes.

## Constructors in Inheritance

If Base Class has a constructor and Derived Class does not, constructor of Base class will run during the creation of Object.  
**If both Base and Derived Classes have a constructor, both will run when an Object of the Derived Class is created.Base Class constructor always runs first.**  

```java
public class Main {
    public static void main(String[] args) {
        Derived obj = new Derived();
    }
}

class Base {
    Base() {
        System.out.println("Base constructor");
    }
}

class Derived extends Base {
    Derived() {
        System.out.println("Derived constructor");
    }
}

// Output :
// Base Constructor
// Derived Constructor
```
>[!IMPORTANT]
**If Base Class Constructor needs arguments, super(args) has to be used**


### Constructor Overloading in Inheritance
```java
public class Main {
    public static void main(String[] args) {
        Derived obj = new Derived();
    }
}

class Base {
    Base() {
        System.out.println("Base constructor");
    }

    Base(int test) {
        System.out.println("Base constructor with parameter " + test);
    }
}

class Derived extends Base {
    Derived() {
        super(1); // Will output Base constructor with parameter 1
        System.out.println("Derived constructor");
    }
}
```
>[!NOTE]
**If super(1) not used then only first constructor (which has no parameters) will run and give same output as previous. When super(1) is used, only second constructor will run ( both constructors cannot run together )**

```java
class Rectangle {
    private final double length;
    private final double breadth;

    protected Rectangle(double length, double breadth) {
        this.length = length; // this is used to differentiate between local whoAreYou variable and class variable
        this.breadth = breadth;
    }

    public double area() {
        return length * breadth;
    }

    public double perimeter() {
        return 2 * (length + breadth);
    }
}

class Square extends Rectangle {
    public Square(double side) {
        super(side, side); // Will Have to give arguments for constructor of Base Class
    }
}

public class Main {
    public static void main(String[] args) {
        Rectangle mySquare = new Square(1);

        System.out.printf("Area : %f\n", mySquare.area());
        System.out.printf("Perimeter : %f\n", mySquare.perimeter());
    }
}
```

## this and super

**this** is used to refer to the class.  
**this.something** is used to refer to any variables/methods of the class.

**super** is used to refer the immediate parent class.
**super.something** is used to refer to any variables/methods of the parent class.
**super()** can be used to invoke parent class constructor.


## Method Overriding

If the Derived Class implements the same method present in the Base Class again, it is known as Method Overriding.    
In that case, Derived Class Method overrides Base Class Method.

>[!NOTE]
Use **@Override** above the Derived Class Method , to know that a Method is being Overriden. When the Base Class Method is modified and if there is no Overriding , it will throw an error to let you know.

```java
class Base {
    public void method() {
        System.out.println("Base Class Method");
    }
}

class Derived extends Base {
    @Override
    public void method() { // will run when whoAreYou() is called on Object of Derived
        System.out.println("Derived Class Method");
    }
}
```

## Dynamic Method Dispatch

When the Reference of Superclass is given to an Object of Subclass, it is called Dynamic Method Dispatch.   

>[!IMPORTANT]
**Only the Methods which are present in Superclass can run.**  
**The Methods which are only present in Subclass cannot run**.  
**When both Superclass and Subclass have same Method(Overriding), Subclass Method will run.**

```java
public class Main {
    public static void main(String[] args) {
        Phone obj = new SmartPhone(); // Reference is Phone, Object is of SmartPhone
        // SmartPhone obj = new Phone() is not valid
        // Can be thought as Every SmartPhone is a Phone, but not every Phone is a SmartPhone
        obj.whoAreYou(); // Will Run SmartPhone Method
        obj.callPolice(); // Will Run (since callPolice is present in Phone and hence also inherited in SmartPhone)
        obj.videoCall(); // Will Not Run
    }
}

class Phone {
    public void whoAreYou() {
        System.out.println("I am a Phone");
    }

    public void callPolice() {
        System.out.println("Calling Police.");
    }
}

class SmartPhone extends Phone {
    public void whoAreYou() {
        System.out.println("I am a SmartPhone");
    }

    public void videoCall() {
        System.out.println("Video Calling...")
    }
}
```