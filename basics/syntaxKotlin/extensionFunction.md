# Функции расширения

[источник](https://metanit.com/kotlin/tutorial/5.5.php)

позволяют добавить функционал к уже определенным типам. При этом типы могут быть определены где-то в другом месте, например, в стандартной библиотеке.

```kotlin
fun тип.имя_функции(параметры) : возвращаемый_тип{
    тело функции
}
```

По своей задумке, функция расширения Kotlin — это дополнительный метод для любого объекта, даже для потенциально несуществующего (нуллабельного). Этот инструмент является прямой реализацией переопределения методов паттерна проектирования Декоратор.

**ВАЖНО:** В функциях расширения мы можем обращаться к любым общедоступным свойствам и методам объекта, однако не можем обращаться к свойствам и методам с модификаторами private и protected.

**ВАЖНО:** Функции расширения не переопределяют функции, которые уже определены в классе. Если функция расширения имеет ту же сигнатуру, что и уже имеющаяся функция класса, то компилятор просто будет игнорировать подобную функцию расширения.