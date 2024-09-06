# Collections

## list

`listOf()`

можно получить сумму с условием 

```kotlin
fun main() {
    val somelist = listOf("a" to 1, "b" to 3, "c" to 2)

    somelist.somOf {
        println(it.second)
    }
}
```
Вывод
`6`
