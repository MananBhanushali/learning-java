# Arrays in Java

```java
datatype []name = new datatype[length];

// Elements can be defined as
name[index] = data;

// Arrays can also be declared as :
int []name = {data1, data2, data3}
```

## Accessing Elements of Array

```java
// Elements of array can be accessed by: 
name [index]

// Index ranges from 0 -> length - 1  

// Length of array can be known by:
name.length
```

>[!NOTE]
Each Element is allocated 4 Bytes of Memory  
Hence, Total Memory occupied by array = length * 4

## Traversing an Array

```java
for (int i = 0; i < name.length; i++) {
    System.out.println(name[i]);
} // Will print all elements of array one by one

```

### Using For Each Loop

```java
for (datatype element: name){
    System.out.println(element);
}
```

## Multidimensional Arrays (Arrays inside arrays)

```java
int[][] array2d; // 2D Array
array2d = new int[2][3]; // Array of 2 elements in which each element is another array of 3 elements

array2d[0][0] = 100;
array2d[0][1] = 101;
array2d[0][2] = 102;
array2d[1][0] = 110;
array2d[1][1] = 111;
array2d[1][2] = 112;

// Traversing a Multidimensional Array
for (int[] element : array2d) { // int[] since element of array2d is an array of int
    for (int element2 : element) { // int since element2 of element is an int
        System.out.println(element2);
    }
}
```