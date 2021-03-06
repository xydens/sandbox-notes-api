# API сервиса заметок

## Задача:

Надо реализовать API для многопользовательского сервиса. Сервис предназначен для хранения заметок.

Заметка — это текстовое поле, длиной до 1000 символов. Заметок у пользователя может быть неограниченное количество. Заметки принадлежат конкретному пользователю, который их создал. Их можно создавать, редактировать, удалять. У заметок надо хранить дату создания и изменения. Пользователь может расшарить конкретную заметку с доступом по ссылке (как в яндекс-диске, гугл-доке и т. п.) для любого неавторизованного пользователя, но только на чтение.

Пользователь характеризуется логином и паролем. Нужно реализовать регистрацию пользователя и авторизацию. Доступ к методам апи должен осуществляться по токену (конкретную реализацию выбираете сами), срок жизни токена должен быть ограничен.

## Запуск и использование

`docker-compose up app` запустит приложение на `http://localhost:300`

http://localhost:3000/api-docs - __Swagger__ страница с документацией и формами для вызова методов API

При авторизации нужно указать только `username` и `password`.`client_id`, `client_secret` заполнять не нужно.


## Автотесты

Для запуска тестов нужно запустить тестовую базу данных. Сделал отдельным сервисом чтобы в результате тестов не затёрлись
данные в основной БД. Команда для запуска `docker-compose up db-test`. Запуск тестов: `yarn test`.

Написал тесты только для сервиса авторизации, потому что в остальном код приложения тривиален. Учитывая короткий жизненный
цикл этого проекта(тестовое задание) полное покрытие тестами тривиального кода представляется мне нерациональным.
