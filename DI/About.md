# DI and source location

Разница может показаться незначительной, но даже при использовании Service Locator класс по-прежнему отвечает за создание своих зависимостей. Для этого он просто использует service locator. С помощью DI класс получает свои зависимости. Он не знает и не заботится о том, откуда они берутся. Одним из важных результатов этого является то, что пример DI намного проще для модульного тестирования, потому что вы можете передать ему макеты реализаций его зависимых объектов. Вы могли бы объединить эти два метода и внедрить локатор служб (или фабрику), если хотите.

Example of using _**Constructor Injection**_:

```Java
//Foo Needs an IBar
public class Foo
{
  private IBar bar;

  public Foo(IBar bar)
  {
    this.bar = bar;
  }

  //...
}
```

Example of using a _**Service Locator**_:

```Java
//Foo Needs an IBar
public class Foo
{
  private IBar bar;

  public Foo()
  {
    this.bar = Container.Get<IBar>();
  }

  //...
}
```

Источник: [тык](https://stackoverflow.com/questions/1557781/whats-the-difference-between-the-dependency-injection-and-service-locator-patte)

# DI on code generation and reflection

### 1. DI на основе кодогенерации

#### Примеры фреймворков:
- **Dagger** (особенно Dagger 2)

#### Как это работает:
- **Кодогенерация** заключается в том, что на этапе компиляции инструмент генерирует код, который управляет созданием и внедрением зависимостей. Этот код статичен и уже скомпилирован вместе с приложением.

#### Плюсы:
- **Высокая производительность**: Так как код создается на этапе компиляции, время выполнения (runtime) не затрачивается на создание зависимостей или выполнение других задач DI. Это делает приложения, использующие DI на кодогенерации, очень производительными.
- **Ошибки на этапе компиляции**: Поскольку код генерируется на этапе компиляции, многие ошибки можно обнаружить заранее, что улучшает надежность приложения.
- **Меньший размер конечного кода**: Сгенерированный код обычно оптимизирован и компактен.

#### Минусы:
- **Сложность настройки**: Настройка фреймворков, основанных на кодогенерации, может быть сложной и требовать глубокого понимания работы DI.
- **Увеличенное время компиляции**: Генерация кода добавляет шаги в процесс компиляции, что может увеличить общее время сборки.
- **Трудность в дебаге**: Поскольку код генерируется автоматически, бывает сложно понять и отследить ошибки в сгенерированном коде.

### 2. DI на основе рефлексии

#### Примеры фреймворков:
- **Koin**

#### Как это работает:
- **Рефлексия** используется для динамического определения зависимостей во время выполнения (runtime). Фреймворк анализирует классы, их аннотации и другие метаданные, чтобы понять, какие зависимости нужно создать и как их внедрить.

#### Плюсы:
- **Простота использования**: DI на основе рефлексии обычно легче настраивать и использовать, что упрощает начало работы с DI для разработчиков.
- **Быстрая итерация**: Так как нет необходимости в генерации кода, время компиляции не увеличивается. Это может ускорить цикл разработки.
- **Гибкость**: Рефлексия позволяет динамически определять зависимости, что делает этот подход более гибким.

#### Минусы:
- **Низкая производительность**: Рефлексия требует дополнительных вычислений во время выполнения, что может снизить производительность приложения, особенно если зависимости создаются часто.
- **Ошибки на этапе выполнения**: Поскольку код не проверяется на этапе компиляции, ошибки могут проявляться уже во время работы приложения, что ухудшает его стабильность.
- **Увеличение размера приложения**: Использование рефлексии может привести к увеличению размера приложения, так как в нем хранятся дополнительные метаданные и механизмы для выполнения рефлексивных операций.

### Сравнение и выбор подхода

1. **Производительность vs. Простота**: Если для вашего приложения критична производительность и вы готовы потратить больше времени на настройку DI, тогда подход на основе кодогенерации (Dagger) будет более подходящим. Если важнее простота настройки и гибкость, Koin на основе рефлексии будет лучшим выбором.

2. **Ошибка на этапе компиляции vs. Ошибка на этапе выполнения**: Если вы хотите как можно раньше обнаруживать ошибки, кодогенерация предоставит вам больше гарантий. Рефлексия может быть полезна, когда нужна гибкость, но при этом вы должны быть готовы к возможным ошибкам во время выполнения.

3. **Увеличенное время сборки vs. Производительность приложения**: Кодогенерация добавляет время на сборку, но это может окупиться более высокой производительностью приложения. Рефлексия же не влияет на время сборки, но снижает производительность во время выполнения.