## The purpose of the task

The purpose of the task is to describe each line in terms of what is happening in the JVM, mentioning the following:
- ClassLoaders,
- memory areas (stack, hip)

```java
public class JvmComprehension { // 0

    public static void main(String[] args) { // 1
        int i = 1;                      // 2
        Object o = new Object();        // 3
        Integer ii = 2;                 // 4
        printAll(o, i, ii);             // 5
        System.out.println("finished"); // 9
    }

    private static void printAll(Object o, int i, Integer ii) { // 6
        Integer uselessVar = 700;                   // 7
        System.out.println(o.toString() + i + ii);  // 8
    }
}
```

Comments:  
0. Application ClassLoader loads the JvmComprehension class
1. main() appears on the stack
2. valiable i of int type is created on the stack and is initialized to 1
3. Bootstrap ClassLoader loads Object class; object Object is created on the heap; variable o of Object type is created on the stack
and assigned a reference to Object object on the heap
4. Bootstrap ClassLoader loads Integer class; object Integer with value 2 is created on the heap; variable ii of Integer type is created on the stack and assigned a reference to Integet object on the heap
5. printAll() appears on the stack
6.variables o of Object type, i of int type and ii of Integer type are created on the stack
7.Integer object with value 700 is created on the heep; uselessVar of Integer type is created on the stack and assigned a reference to Integer object on the heap
8. Bootstrap ClassLoader loads System class, toString() appears on the stack, println() appears on the stack
9. Bootstrap ClassLoader loads String class, String object with value finished is created on the heap, println() appears on the stack
