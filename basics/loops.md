# Loops in Java

## If Else Loop

```java
if ( condition ){ code }
else if ( condition ){ code }
else { code }
```

## Switch Case ( If Else Ladder Alternative)

```java
switch( variable ){
    case <value1>: // Like If Else
        code
        break; // If break not mentioned, all the other case snippets will also run once any condition matches
    case <value2>:
        code
        break;
    case <value3>:
        code
        break;
    default: // Like Else
        code
}
```

**Enhanced Switch**

```java
switch( variable ){
    case <value1> -> code;
    case <value2> -> code;
    case <value3> -> code;
    default -> code;
}
```

## While Loop
```java
int i = 1;
while ( i<=3 ){ // Will Run 3 times
    code
    i++;
}
```

### Do While
```java
int i = 1;
do {  // Will Run the first time even if condition not true
    code
    i++
 }
while ( condition );
```