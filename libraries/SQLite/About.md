Насчет закрытия БД.
В одной, очень содержательной, дискуссии, Диана Хакборн (Dianne Hackborn), далеко не последний человек в подразделении андроид гугла, объясняла всем заинтересованным гражданам, что подключение к БД не только не надо закрывать, а что это еще и не очень то хорошо - закрывать это подключение.
При закрытии приложения/класса, использующего подключение к БД, сборщик мусора уничтожит и классы БД и все будет в норме, в противном же случае происходят какие то страшные вещи.

UPDATE

Вот обсуждение на SO - там есть ссылка на дискуссию гугл-груп андроид-разработчиков, где своим мнением делится Марк Мерфи и Диана. Думаю обсуждение на SO тоже будет интересно.

UPDATE2

В своих проектах я использую Realm и вообще не заморачиваюсь с БД SQLite, уже даже и не вспоминаю эти классы-помошники, курсоры, открытия-закрытия , множество всяких оберток и прочий "ужас" ... Все быстро, очень удобно и просто - работаешь, как с ORM (по принципу классов-моделей), но это нативная БД без прослоек и без SQLite

[источинк здесь](https://ru.stackoverflow.com/questions/427863/Закрытие-классов-базы-данных-курсоров)