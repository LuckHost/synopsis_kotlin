# Основы основ в основе

### Статический метод

**Особенности статического метода:**

- Статический метод тот, который является частью класса, а не его экземпляром
- Каждый объект класса имеет доступ к этому методу
- Статические методы имеют доступ к переменным класса (static variables) без использования объекта класса (instance)
- Статический метод может получить доступ только к статическим данным.
- К статическим методам можно обращаться напрямую везде

**Синтаксис:**
- Cтатический метод: `Object.methodname()` 
- Обычный: `className.methodname()`