# Channel

Инструмент для связи между корутинами, напоминает очередь

Еще можно назвать "синхронизацией через коммуникацию"

Работает до тех пор, пока его не закроют

Не останавливает поток, при чтении корутиной, останавливает саму корутину 

Изначально не имеет буфера, по этим причинам, когда какая-либо корутина обращается к каналу, то он ее приостанавливает, ждет, пока появятся корутины, которые ожидают данных из канала и, когда такие появляются, возобновляет работу первой крутины, устраивая им "свидание"

### Сатндартные размеры буфера

- **REBDEZVOUS** Без буфера, дефолтное значение для любого Channel
- **CONFLATED** Размер буфера = 1, хранит одно значение
- **BUFFERED** Задает стандартный размер буфера, котоырй определен в свойствах окружения (64 по умолчанию)
- **UNLIMITED** Максимально возможный размер буфера (int.MAX_SIZE)

### Flow и Channel

Channel более легковесный, более сложный в синтаксисе и взаимодейстует напрямую с корутинами. На данный момент Flow является более перспективным решением, нежели Channel 