# Кратко о Java Virtual Machine

JVM позвоняет заупскать написанные программы на разных ОС.

Икходный код -> байт код -> машинный

Из исходного в байт код помогает перейти компилятор (javac)

Из байт кода в машинный переводит уже JVM


# Память
---

### Куча (Heap)

используется для хранения объектов (экземляров класса)

Хранит объекты внутри себя по адрессам со всеми параметрами внутри 

### Стэк (Stack)

Структура данных, относится не только к JVM

Используется для хранения порядка вызова функций (методов) и для хранения ссылок на объекты. Работает по приципу "Последний вошел - первый вышел"
Last in first out (LIFO)

Последний добавленный элемент обрабатывается в последнюю очередь

Есть две операции
- Добавить элемент (Push) добавляемый становится верхним
- Получить (Pop) возвращается последний элемент и он же удаляется из стека

### Стэк в JVM

Стэк вызова методов

Туда кладутся методы и то, откуда они были вызваны. После окончания работы из стека эта функция удаляется из стека

### Связь между стэком и кучей

В функциях в стеке хранятся не только параметры функции, но и ссылки на объекты в куче 

### String pool 

Так как строки часто используются для экономии памяти был создан string pool

Когда происходит создание новой строки, то сначала проверяется наличего ее в пуле строк, если она там есть, то переменной присваивается ссылка на нее. Иначе - создается строка и возвращается ссылка и присваивается переменной.