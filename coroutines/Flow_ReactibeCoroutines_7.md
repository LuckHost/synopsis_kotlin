# Flow 

холодный асинхронный поток данных, котоырй может законится успешно, либо неуспешно

имеет
- стандартные операторы
- промежуточные (модификация потока)
- терминальные (запуск данных из flow)

не всегда бывает холодным

# Создание Flow

```kotlin
flowOf(1)
flowOf("a", "b")
listOf("a", "b").asFlow()
```
```kotlin
fun fibonacci(count: Int) = flow {
  reqire(count >= 1) { "count must be positive value" }
  emit(1)

  if (count >= 2) emit(2)

  var previous = 1
  var current = 1

  for (i ni 3..count) {
    val a = current
    current += previous
    previous = a
    emit(currernt)
  }
}
```
### Flow bulider
это функции, которые создают flow

### Терминальные операторы

вызываются из корутин, либо 

flow<T>.launchIn(scope)

### Кэширование 

flow.buffer(
  capacity = Channel.BUFFERED,
  onBufferOverflow = BufferOverflow.SUSPEND
)

собирает данные и передает коллектору не тормозя flow