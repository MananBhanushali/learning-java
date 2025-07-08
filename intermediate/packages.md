# Packages in Java

### Is Java interpreted or compiled?

**Java is a hybrid language (both compiled as well as interpreted)**

![Compiler Interpreter Process](packages.png)

The **.java** file is system-specific.  
It is compiled into a **.class** system-independent file by the command :  
```
javac name.java
```

Each Class in the name.java file compiles to give individual .class files.

The name.class file that gets generated contains bytecode and can be shared and executed by anyone using any system( by JVM - interpreter) using the command :
```
java name
```

Hence, **Java is platform independent.**

## Packages

A Package is used to group related Classes.
They help in avoiding name conflicts.

There are two types of packages:  
1. Built-in ( Java APIs )
2. User Defined ( Custom Packages )

Packages can be imported in multiple ways:  
```java
import java.util.Scanner
import java.util.* // Imports everything from java.util

java.util.Scanner sc = new java.util.Scanner(System.in) //  Directly uses Scanner
```

### Creating a Java Package

In the name.java file, specify package name 

```java
package com.company;

public class name {
    public static void main(String[] args) {

    }
}
```

And then Run javac with an additional argument -> -d \<output-folder>

```
javac -d . name.java
```

This will generate the name.class file inside .\com\company 

>[!NOTE] 
**-d \<directory> command:**  
Sets the destination directory for class files. The destination directory must already exist;  
javac will not create the destination directory.  
If a class is part of a package, javac puts the class file in a subdirectory reflecting the package name, creating directories as needed.  
For example, if you specify -d /home/myclasses and the class is called com.mypackage.MyClass, then the class file is called /home/myclasses/com/mypackage/MyClass.class.  
If -d is not specified, javac puts the class file in the same directory as the source file.


