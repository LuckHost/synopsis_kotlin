# Custom view

Зачем вообще надо?
Если вдруг нам нужно что-то уникальное, чего нет в библиотеках

К примеру какой-то супер календарь с изображением статистики или графиками.

Для создания нужно создать класс-наследник от View()

```kotlin
class TestView(
    context: Context, attributeSet: AttributeSet
) : View(context, attributeSet) {
    override fun onDraw(canvas: Canvas) {
        super.onDraw(canvas)
        // прорисовка элемента
        canvas.drawCircle(width / 2f, height / 2f, radius, paint)
    }
}
```