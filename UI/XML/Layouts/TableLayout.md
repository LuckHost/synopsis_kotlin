# TableLayout 

[источник](https://developer.alexanderklimov.ru/android/layout/tablelayout.php)

Разметка `TableLayout` (Табличная разметка) позиционирует свои дочерние элементы в строки и столбцы, как это привыкли делать веб-мастера в теге table. `TableLayout` не отображает линии обрамления для их строк, столбцов или ячеек. `TableLayout` может иметь строки с разным количеством ячеек. При формировании разметки таблицы некоторые ячейки при необходимости можно оставлять пустыми. При создании разметки для строк используются объекты TableRow, которые являются дочерними классами `TableLayout` (каждый TableRow определяет единственную строку в таблице). Строка может не иметь ячеек или иметь одну и более ячеек, которые являются контейнерами для других объектов. В ячейку допускается вкладывать другой `TableLayout` или LinearLayout.

`TableLayout` удобно использовать, например, при создании логических игр типа Судоку, Крестики-Нолики и т.п.

Вот несколько правил для `TableLayout`. Во-первых, ширина каждой колонки определяется по наиболее широкому содержимому в колонке. Дочерние элементы используют в атрибутах значение match_parent. Атрибут TableRow для layout_height всегда wrap_content. Ячейки могут объединять колонки, но не ряды. Достигается слияние колонок через атрибут layout_span.

Если атрибуту android:stretchColumns компонента `TableLayout` присвоить значение "*", то содержимое каждого компонента TableRow может растягиваться на всю ширину макета.

Если текст в ячейке таблицы слишком длинный, то он может растянуть ячейку таким образом, что часть текста просто выйдет за пределы видимости. Чтобы избежать данной проблемы, у контейнтера `TableLayout` есть атрибут `android:shrinkColumns`. Мы рассмотрим программное применение данного атрибута через метод `setColumnShrinkable()`.




