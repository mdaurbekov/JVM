public class JvmComprehension {

    public static void main(String[] args) {
        int i = 1;                      // 1    Cоздаётся фрейм main() в стеке. Переменная int i и ее значение сохраняются во фрейме main()
        Object o = new Object();        // 2    Ссылка на объект о во фрейме main(), сам объект в Heap
        Integer ii = 2;                 // 3    Ссылка на объект ii во фрейме main(), сам объект в Heap
        printAll(o, i, ii);             // 4    Создаётся новый фрейм printAll() в стеке
        System.out.println("finished"); // 7    Сохранение параметров, освобождение места в стеке по завершению.
    }

    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5   Ссылка на объект о во фрейме printAll(), сам объект в Heap.
        System.out.println(o.toString() + i + ii);  // 6   Создаётся новый фрейм в стеке System.out.println.
    }
}