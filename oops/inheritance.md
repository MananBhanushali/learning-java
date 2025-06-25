# Inheritance in Java

Inheritance means deriving new things from existing things.  
**Derived Class( subclass ) inherits all (not private) properties (methods, variables) from its Base Class( superclass ).**

```java
class Base {
    printBase() {
        System.out.println("This is a method of the Base Class");
    }
}

class Derived extends Base { // Derived Class will also inherit printBase method from Base Class
    printDerived() {
        System.out.println("This is a method of the Derived Class");
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
        this.length = length; // this is used to differentiate between local method variable and class variable
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

### this and super

**this** is used to refer to the class.  
**this.something** is used to refer to any variables/methods of the class.

**super** is used to refer the immediate parent class.
**super.something** is used to refer to any variables/methods of the parent class.
**super()** can be used to invoke parent class constructor.
