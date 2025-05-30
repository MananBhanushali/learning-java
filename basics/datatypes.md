# Data Types in Java

- Primitive (Intrinsic)
    1. byte
        - Takes 1 byte
        - Default value is 0
        - Value ranges from -128 to 127
    2. float
        - Takes 4 bytes
        - Default value is 0.0f
    3. char
        - Takes 2 bytes (Supports Unicoode)
        - Default value is '\u0000'
        - <ins>**Value ranges from 0 to 2^16 - 1**</ins> (Since it can only be positive)
    4. bool
        - Size Depends on JVM
        - Value can be true or false
        - Default value is false
    5. int
        - Takes 4 bytes
        - Default value is 0
        - Value ranges from -2^31 t0 2^31 - 1
    6. long
        - Takes 8 bytes
        - Default value is 0
        - Value ranges from -2^63 t0 2^63 - 1
    7. double
        - Takes 8 bytes
        - Default value is 0.0d
    8. short
        - Takes 2 bytes
        - Default value is 0
        - Value ranges from -2^15 t0 2^15 - 1
- Non Primitive (Derived)

>[!NOTE]
Value range of a datatype --> [ - 2^(n-1) , (2^n-1) - 1]  
(where n is number of bits)  
\
Ex) byte = 8 bits --> n = 8  
    Value range --> [-2^7 , 2^7 - 1]

## Variables
```java
<datatype> <name> = <value>;
```