# SOLID принципы 

Принципы написания кода таким образом, чтоб его было легко расширять.

SOLID - аббревиатура, где каждая буква означает паттерн 

- **SRP** - [Single Responsibility Principle](./SRP.md). Принцип единственной ответственности. Каждый файл, блок, структура должна отвечать только за 1 задачу
- **OCP** - [Open Close Principle](./OCP.md). Принцип открытости-закрытости. Функции, классы и тд. должны быть открыты для расширения и закрыты для изменения
- **LSP** - [Liskoff Substitution Principle](./LSP.md). Дети классов не должны изменять уже написанную логику родителей.
- **ISP** - [Interface Segregation Principle](./ISP.md). Принцип разделения интерфейсов.
- **DIP** - [Dependency Invertion Principle](./DIP.md). Принцип инверсии зависимости. Верхние модули не должны зависеть от модулей нижних уровней. Все должно зависить от абстракции