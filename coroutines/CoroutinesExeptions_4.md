# try-catch

launch и async нужно обрабатывать по разному

```kotlin
val job = launch {
    val child = launch {
        try {
            delay(Long.MAX_VALUE)
        } finally {
            println("Child is cancelled")
        }
    }
}

//Cancelling child
//Child is cancelled
//Parent is not cancelled
```

```kotlin
val deferred: Deferred<Data> = async {
  doSomething()
}

try {
  deferred.await()
} catch (e: Exception) {
  // catching
}
```

# подписка на результат job

job.invokeOnCompletion

# для закрытия потока можно использовать 

withContext(NonCancellable)

но лучше этим не увлекаться 
