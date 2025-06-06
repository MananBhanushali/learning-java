# Strings in Java

- **String is a class in Java but it can be used as a datatype**

```java
String test = new String("test"); // Like Object
OR
String test = "test"; // Like Datatype
```

- Strings are immutable ( cannot be changed )

## Methods in String
- .length()
- .toLowerCase()
- .toUpperCase()
- **.trim()** -> Removes Leading and Trailing Spaces
- **.subset( \<begin-index>, \<end-index> )** -> Returns a Substring from \<begin-index> to \<end-index> (\<end-index> is optional)
- .replace('find', 'replace')
- .startsWith("char") -> Returns boolean
- .endsWith("char") -> Returns boolean
- **.charAt( \<index> )** -> Returns the char at given index
- **.indexOf("string", \<from-index>)** ->Returns the index of the given string from the given index. Will return -1 if not found. **If string has multiple letters, index of the first letter is returned**
- **.lastIndexOf("string", \<from-index>) ->Returns the position of the last occurrence of specified character(s) in a string , searching backward starting at the specified index.** If string has multiple letters, index of the first letter is returned. **[ [ Docs ](https://www.geeksforgeeks.org/java-lang-string-lastindexof-method/) ]**
- .equals("str") -> Returns boolean
- .equalsIgnoreCase("str") -> Returns boolean

## Escape Characters
- Newline ( \n )
- Tab ( \t )
- Single Quote ( \' )
- Backslash ( \\ )