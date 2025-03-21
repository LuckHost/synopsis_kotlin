## Модульность

[источник](https://developer.android.com/topic/modularization/patterns)

Относится к **Android** разработке

Модульность позволяет разбить приложение на блоки со своими Gradle зависимостями
Данные блоки должны быть слабо связаны. Это позволяет масштабировать проект проще и легче.

Помимо всего прочего модули легче тестировать

Есть три оценки модульной базы
- **Связность** *(cohesion)* - все модули работают как единая система, где каждый имеет свою обязанность
- **Взаимодействие** *(coupling)* - модули должны быть максимально независимы, чтобы изменения в одном не влекли много изменений в других
- **Гранулярность** *(granularity)* - количетсво модулуй в базе относительно их размера 


### Пример Яндекса

[источник](https://habr.com/en/companies/yandex/articles/584756/)


##### Feature modules

В API модуля лежит два пакета

- api
    - Публичный интерфейс
    - Один публичный фрагмент
- internal
    - Internal фрагменты

Все вложенные фрагменты - дочерние
Эти модули могут содержать DI

##### Core modules

Модуль, который содержит логику, вспомогательны код, общий для нескольки фич

**Ключевое отличие** - core-модули могут зависеть друг от друга, а вот feature-модули - нет