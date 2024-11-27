# Doze Mode

[очень хороший источник, рекомендуемо для прочтения](https://habr.com/ru/companies/broadcast/articles/734236/)

Режим, когда телефон определяет режим бездействия и ограничивает приложения, не давая им тратить батарею

### История

Был добавлен в Android 6, после чего постоянно расширялся и накладывал еще больше ограничений 

На данный момент BroadcastReciver довольно сильно ограничен по сравнению с начальным видом и имеет такие сообщения

- ACTION_BOOT_COMPLETED;

- ACTION_LOCAL_CHANGED;

- ACTION_PACKAGE_DATA_CLEARED и ACTION_PACKAGE_ FULLY_REMOVED;

- ACTION_NEW_OUTGOING_CALL;

- ACTION_MEDIA_***;

- SMS_RECEIVED_ACTION и WAP_PUSH_RECEIVED_ACTION.

### App Standby 

Это состояние, когда приложение свернуто и на него наложены различные ограничения, такие как ограничения выхода в сеть и снижение частоты срабатываний различных событий

### Firebase Cloud Messaging High Priority

Есть такой вид пушей, который может разбудить устройство из Doze Mode. Называются они High Priority Push 

Но даже такие пуши - не гарант вывода устройства из Doze Mode

Нужны они для действительно важных событий (сообщение от приложения, где есть уведомление)