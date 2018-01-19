# OneScript RabbitMQ

[![Build status](https://ci.appveyor.com/api/projects/status/kbqiv9rsp1ohghqb/branch/master?svg=true)](https://ci.appveyor.com/project/nixel2007/oscript-rabbitmq/branch/master)

## Поддержка RabbitMQ для OneScript

## Установка

### С хаба пакетов

`opm install rabbitmq`

### С релизов GitHub

1. Перейти на [страницу релизов](https://github.com/silverbulleters/oscript-rabbitmq/releases)
1. Скачать артефакт RabbitMQ-x.y.z.ospx
1. Установить с помощью opm: `opm install -f RabbitMQ-x.y.z.ospx`

### С AppVeyor

1. Перейти на страницу [последней сборки](https://ci.appveyor.com/project/nixel2007/oscript-rabbitmq) или [истории сборок](https://ci.appveyor.com/project/nixel2007/oscript-rabbitmq/history) и выбрать интересующую сборку
1. Перейти в раздел Artifacts
1. Скачать артефакт RabbitMQ-x.y.z.ospx
1. Установить с помощью opm: `opm install -f RabbitMQ-x.y.z.ospx`

## Использование

### Отправка сообщения (BasicPublish)

```bsl
#Использовать RabbitMQ

Соединение = Новый СоединениеRMQ;
	
Соединение.Пользователь = "guest";
Соединение.Пароль = "guest";
Соединение.Сервер = "localhost";
Соединение.ВиртуальныйХост = "/";
	
Клиент = Соединение.Установить();
ИмяТочкиОбмена = "test";
Клиент.ОтправитьСтроку("Привет", ИмяТочкиОбмена);
	
Соединение.Закрыть();

```

### Получение сообщения (BasicGet)

```bsl
#Использовать RabbitMQ

Соединение = Новый СоединениеRMQ;
	
Соединение.Пользователь = "guest";
Соединение.Пароль = "guest";
Соединение.Сервер = "localhost";
Соединение.ВиртуальныйХост = "/";
	
Клиент = Соединение.Установить();
ИмяОчереди = "test";
СообщениеИзОчереди = Клиент.ПолучитьСтроку(ИмяОчереди);
	
Соединение.Закрыть();

```

## Список методов

Список методов и их описание доступны в каталоге [doc](doc)
