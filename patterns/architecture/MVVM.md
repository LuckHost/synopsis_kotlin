# Model View ViewModel

Паттерн модуля представления,который структуризирует логику View, отделяя бизнес логику от UI 

### Причины использования:

- **Перенос части логики** в другой класс
- **Сохранение состояния** activity. Не так актуально в jetpack compose, но все еще поелезно 


### Особенности:

- **ViewModel** ничего не знает об activity 
- **ViewModel** НЕ должно иметь никакого _**context**_
- **ViewModel** не должно ничего возвращать, там не должно быть никаких _**return**_ 
- **Activity** следит за ViewModel
- **Activity** не должна иметь возможность менять что-то в ViewModel

### Полезное

Можно использовать Sealed классы для livedata или других стейтов, это более продвинутый вариант 