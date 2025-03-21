# Архитектурные паттерны

Это паттерны, которые помогают проектировать архитектуру приложения

К примеру UI паттерны

- **MVC** 
- **MVP**
- **MVI**
- **MVVM**

Все они немного разные, но имеют общие модули и служат для одного: **отделить UI логику от бизнес логики**

#### Общие компоненты

**ViewModel** - класс, который содежит бизнес логику приложения, а также имеет в своем арсенале все методы, runtime-данные, логические переменные, которые используются в userstory. Иногда часть логики вынесена за ViewModel, а сам он ее просто вызывает в нужный момент (Clean Architecture)

**Model** - POJO (Plain old Java object - старый добрый Java-объект), не реализует никакой логики, просто является шаблоном модели(моделей), 