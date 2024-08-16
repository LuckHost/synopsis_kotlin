### LiveData

**LiveData** — это класс, который является частью Android Jetpack и представляет собой контейнер данных, который позволяет наблюдать за изменениями данных в рамках жизненного цикла Android-компонентов (например, `Activity` или `Fragment`).

#### Основные особенности LiveData:
- **Привязан к жизненному циклу:** LiveData автоматически управляет подписчиками в зависимости от жизненного цикла компонента (например, если `Activity` или `Fragment` уничтожаются, LiveData автоматически удаляет соответствующие наблюдатели).
- **Однократная отправка данных:** LiveData по умолчанию отправляет данные только активным наблюдателям. Это значит, что новые подписчики получают последнее значение, только если они становятся активными (например, `onResume`).
- **Нет backpressure:** LiveData не поддерживает backpressure (управление потоком данных), и она всегда хранит только одно значение.
- **Ориентирован на работу с UI:** LiveData обычно используется в архитектуре MVVM для передачи данных между ViewModel и UI-компонентами.

### Пример использования LiveData:
```kotlin
val data: LiveData<String> = MutableLiveData()

// Подписка на изменения
data.observe(this, Observer { newValue ->
    // Обновить UI
})
```