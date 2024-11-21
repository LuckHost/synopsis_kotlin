# Dispatcher 

Определяет пул потоков/поток использования корутин


Всего есть 6 видов 

- Default
- Main
- Unconfined
- IO
- newSingleThreadContext
- newFixedThreadPoolContext


### Default

Стандартный, используется везде по умолчанию, если тип диспатчера не указан явно

Использует общий пул разделяемых фоновых потоков

Подходит для выполнения операций, не связанных с вводам-выводом и которые требуют ресурсов ЦП

#### IO

Для IO операций 

>Ввод-вывод (от англ. input/output, I/O) в информатике — взаимодействие между обработчиком информации (например, компьютером) и внешним миром.
>
>Ввод — сигнал или данные, полученные системой.
Вывод — сигнал или данные, посланные ею (или из неё).

Использует общий пул потоков. Предназначен для операций, которые не сильно требуют мощности ЦП

Не нагружает сильно систему

#### Main
по умолчанию не определен

для главного потока 

#### Unconfined
изначально не требует какго либо потока
занимает поток, в котором создался и запустился

Не рекомендуется использовать 

#### newSingleThreadContext и newFixedThreadPoolContext

Позволяют вручную создать поток/пул потоков

---
желательно создать обертку и засунуть ее в Di, а потом уже использовать 
---

```kotlin
class AppDispatchers(
    val main: MainCoroutineDispatcher = Dispatchers.Main,
    val default: Coroutine Dispatcher = Dispatchers.Default,
    val io: CoroutineDispatcher = Dispatchers.IO,
    val unconfined: Coroutine Dispatcher = Dispatchers.Unconfined,
)
class ViewModel @Inject constructor(dispatchers: AppDispatchers)
```