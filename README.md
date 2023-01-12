* добавила еще три номера строк - 0, 1, 6


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
    }}

Комментарии:
0 - Application ClassLoader загружает класс JvmComprehension
1 - main() попадает в стек
2 - в стеке создается перемпенная i типа int и инициализируется 1
3 - Bootstrap ClassLoader загружает класс Object; в куче создан объект Object; в стеке создана переменная о типа Object
и ей присвоена ссылка на объект Object в куче
4 - Bootstrap ClassLoader загружает класс Integer; в куче создан объект Integer со значением 2; в стеке создана переменная ii типа Integer
и ей присвоена ссылка на объект Integer в куче
5 - printAll() попадает в стек
6 - в стеке созданы переменные o типа Object, i типа int, ii типа Integer 
7 - в куче создан объект Integer со значением 700; в стеке создана переменная uselessVar типа Integer
и ей присвоена ссылка на объект Integer в куче
8 - Bootstrap ClassLoader загружает класс System, toString() попадает в стек, println() попадает в стек
9 - Bootstrap ClassLoader загружает класс String, в куче создан объект String со значением finished, println() попадает в стек