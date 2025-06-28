## Classes in Java

A Class is a blueprint/template.  
The instance of a Class is called an Object.  
Memory is alloted only after Object instantiation. 

```java
class Employee { // Defining a Class
    String name; // Attributes of a Class
    int salary;

    void paySalary(){ // Methods of a Class
        System.out.printf("$%d salary paid to Employee: %s", salary, name);
    }
}

public class Main {
    public static void main(String[] args) {
        Employee john = new Employee(); // Creating Object (Instance of Class)
        john.name = "John Doe";
        john.salary = 1000;
        john.paySalary();
    }
}
```

>[!NOTE]
There can only be one public class in a file (which is named as the filename).