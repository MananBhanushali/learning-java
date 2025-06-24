# Constructors in Java

Constructor Method gets called automatically when the Instance of a Class (Object) gets created.  
**The Method named just as the Class Name acts as the Constructor**

```java
class Employee {
    private int id;
    private String name;

    Employee() {
        this.id = 0;
        this.name = "ENTER_YOUR_NAME";
    }
}
```

>[!IMPORTANT]
Constructor can also have parameters.The parameters of the constructor will then have to be given a value during the creating of the Object

```java
class Employee {
    private int id;
    private String name;

    Employee(int id, String name)) {
        this.id = id;
        this.name = name;
    }
}

// WHile creating the Object
Employee john = new Employee(1, "John Doe");
```