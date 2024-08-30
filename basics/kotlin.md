### Примитивы 

В Kotlin нет примитивных типов int, float, double и т. д., всё является объектами. 
Вместо примитивных типов используются объекты: 
- Byte; 
- Short; 
- Int (не Integer как в Java); 
- Double; 
- Char; 
- Float; 
- Long; 
- Boolean. 

### Диапозоны

```kotlin
1..10

1 until 10

10 douwntil 1

0..100 step 10
```

### vararg

```kotlin
fun main() {
  someFun(1, 2, 3, 4)
  someFun(*intArrayOf(1, 2, 3, 4), 5, 6, 7)
}


fun someFun(vararg numbers: Int) {
  // do something
}
```

### data class

Data class — это специальный тип класса в языке программирования Kotlin, предназначенный для представления небольших, простых объектов данных.

Преимущества дата-классов по сравнению с обычными классами:

- Автоматическое создание конструктора с параметрами, соответствующими именам свойств класса.
- Автоматическое создание методов equals(), hashCode() и toString(), что упрощает сравнение объектов и сериализацию.
- Автоматическое создание метода copy(), который позволяет создавать новый экземпляр data class с изменёнными значениями некоторых свойств.
- Data class можно использовать для представления следующих типов объектов