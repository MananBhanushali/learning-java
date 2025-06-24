# Access Specifiers in Java

1. private
2. public
3. protected
4. default
---
1. **private**

Cannot be Accessed (Viewed/Modified) outside the class (not even by its own Object). Hence they can only be accessed from the Methods in their Class

>[!IMPORTANT]
Getters and Setters are used to View/Modify the attributes, so that any functions can be carried out while getting/setting an attribute or performing any checks.

```java
public class Employee {
    private int id;
    String name;

    public int getId() {
        return id;
    }

    public int setId(int id) {
        this.id = id;
    }
}
```

2. **public** - visible to all classes everywhere
3. **protected** - can only be accessed within its own package and, in addition, by a subclass of its class in another package.
4. **default** ( also known as **package-private**) - visible only within its own package


## References 
[Oracle Docs Access Specifiers](https://docs.oracle.com/javase/tutorial/java/javaOO/accesscontrol.html)