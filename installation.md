# Установка

## Установка библиотек

[.Net core 2.2 SDK](https://dotnet.microsoft.com/download)
[node.js + npm](https://nodejs.org/en/download/)
[Quasar CLI](https://quasar.dev/quasar-cli/installation)
СУБД на ваш выбор

## Установка SunEngine

Склонируйте с гитхаба репозиторий фреймворка в папку SunEngine:

```
git clone https://github.com/Dmitrij-Polyanin/SunEngine.git SunEngine
```

## Конфигурация сервера

Скопируйте демонстрационную папку конфига `SunEngine.Cli/Config-template` в `SunEngine.Cli/local.mysite.com.Config`.

Внутри отредактируйте `DataBaseConnection.json` - задайте название базы данных, логин, пароль и порт для доступа к БД.

Создайте базу данных с указанным именем при помощи вашего любимого инструмента работы с вашей БД.

Запустите миграцию (создание таблиц) и сидинг (заполнение начальными данными):

```
dotnet run migrate init seed
```

Сиды для категорий, меню, ролей пользователей и тестовых пользователей находятся в папке конфига.

## Конфигурация клиента

```
cd Client
npm install
```

## Запуск сервера

```
dotnet run server
```

## Запуск клиента

```
quasar dev
```
