# Iterator

[источник для Kotlin](https://kotlinlang.ru/docs/iterators.html?ysclid=m3mdfw84xf376708875)
[источник для Java](https://metanit.com/java/tutorial/5.10.php?ysclid=m3mdb1cvcp967668829)

Объект коллекции, который позволяет получить доступ к элементам, не раскрывая базовую структуру

### Java

Интерфейс итератора в Java. Коллекция возвращает объект, реализующий его

```Java
public interface Iterator <E>{
     
    E next();
    boolean hasNext();
    void remove();
}
```

Помимо этого существует ListIterator, который расширяет интерфейс Iterator, добавляя новые методы

- void add(E obj): вставляет объект obj перед элементом, который должен быть возвращен следующим вызовом next()

- boolean hasNext(): возвращает true, если в коллекции имеется следующий элемент, иначе возвращает false
 
- boolean hasPrevious(): возвращает true, если в коллекции имеется предыдущий элемент, иначе возвращает false
 
- E next(): возвращает текущий элемент и переходит к следующему, если такого нет, то генерируется исключение NoSuchElementException
 
- E previous(): возвращает текущий элемент и переходит к предыдущему, если такого нет, то генерируется исключение NoSuchElementException
 
- int nextIndex(): возвращает индекс следующего элемента. Если такого нет, то возвращается размер списка

- int previousIndex(): возвращает индекс предыдущего элемента. Если такого нет, то возвращается число -1

- void remove(): удаляет текущий элемент из списка. Таким образом, этот метод должен быть вызван после методов next() или previous(), иначе будет сгенерировано исключение IlligalStateException

- void set(E obj): присваивает текущему элементу, выбранному вызовом методов next() или previous(), ссылку на объект obj

### Kotlin

В Kotlin итераторы доступны всем наследникам класса `Itarable<T>`. Для его полуения нужно вызвать метод `.iterator()`

Помимо этого существует `ListIterator` и `MutableIterator`, который добавляет возможность удаления и вставки элементов

## Безопасный способ удаления элемнтов

С помощью интератора можно и нужно удалять элемнты коллекции, так как он позволяет пройтись по элементам коллекции последовательно.

В Java при удалении элемента во время прямой итерации может быть выдана ошибка ConcurrentModificationException. Возникает во время итерирования при модификации 