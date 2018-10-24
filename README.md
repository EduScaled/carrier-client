
# Описание

Python-пакет, обеспечивающий коммуникацию между Carrier (https://github.com/EduScaled/carrier) и  3th-party приложением

Используемый стек: ```python3.7```

# Установка

1. В вашем виртуальном окружении выполнить комманду ```pip install git+https://github.com/EduScaled/carrier-package```

# Использование

**Раздел будет доработан.**

Пакет представлен тремя основными объектами, а именно ```IncomingMessage```, ```OutgoingMessage``` и ```MessageManager```.

Первые два объекта отвечают, соответственно, за входящие и исходящие сообщения.  Третий объект позволяет обрабатывать полученные и отправлять исходящие сообщения.

```IncomingMessage``` имеет class-method ```create_from_bytes```, который в качестве параметра принимает последовательность байт (предположительно, от входящего http-запроса), который на основе этих данных создает и возвращает объект  ```IncomingMessage```. **Валидации объекта пока не производится, при передачи неверной последовательности приведет вызову ошибки**. С полученным объектом уже можно производить произвольные манипуляции. Предполагается дальнейшая его передача в объект ```MessageManager``` для обработки зарегистрированных в данном объекте обработчиков событий.

```OutgoingMessage``` - объект, содержащий информацию для отправки.
Создается стандартным конструктором, передается два параметра - ```topic``` и ```message``` (**формат передаваемого сообщения пока не определен, предполагается ...**) . 

```message = OutgoingMessage(topic="<topic>", message="<message>")```

