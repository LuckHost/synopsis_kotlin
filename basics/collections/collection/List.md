# List

Крутая шутка чтоб хранить объекты 

Является родителем нескольких типов типов 

- ArrayList
- Vector
- LinkedList

## штука с собеса рандомного

`listOf()`

можно получить сумму с условием 

```kotlin
fun main() {
    val somelist = listOf("a" to 1, "b" to 3, "c" to 2)

    somelist.sumOf {
        println(it.second)
    }
}
```
Вывод
`6`