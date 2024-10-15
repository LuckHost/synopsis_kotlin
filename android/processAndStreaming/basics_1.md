# Компоненты 

Если приложение запускается, то строится "точка входа" с одним главным потоком, который еще называют "UI" потоком

## Приоритеты ситстемы в процессах

1. Процесс на экране пользователя 
2. Компоненты, которые видны, но не переднем плане
3. Виджеты взаимодействия помимо экрана (музыка, геолокация, др.)
4. Процессы, которые были остановлены

**Все межпроцессные** операции происходят на главном потоке