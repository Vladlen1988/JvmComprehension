### Описание с точки зрения происходящего в JVM
```java
public class JvmComprehension {
public static void main(String[] args) {
int i = 1;                      // 1
Object o = new Object();        // 2
Integer ii = 2;                 // 3
printAll(o, i, ii);             // 4
System.out.println("finished"); // 7
}

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5
        System.out.println(o.toString() + i + ii);  // 6
    }
}
```
Загрузка с помощью СlassLoader, далее идет связывание и инициализация.  

1. Инициализируется переменная i и попадает в Stack memory.   
2. Создается ссылка на объект d heap (куча) и сам объект в Stack.  
3. Инициализируется переменная ii и попадает в Stack memory.  
4. Создается фрейм метода printAll в Stack. 
5. Инициализируется переменная uselessVar и попадает в Stack memory.  
6. Создается фрейм в Stack и передается ссылка на объект.  
7. Создается фрейм в Stack и ссылка на строку в куче.  

Сборка мусора.
