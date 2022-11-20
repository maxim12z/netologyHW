[Задание](https://github.com/netology-code/ibweb-homeworks/tree/master/01_arch)

## Задание1  Карта взаимодействия
```
Client ---> Server1 (Запрос).
    PUT /users HTTP/1.1  
    Content-Type: application/x-www-form-urlencoded\r\n
    Form item: "login" = "user"
    Form item: "password" = "111111"
    
Server1 ---> Client (В ответ получаем токен)
    HTTP/1.1 200 OK\r\n
    Content-Type: application/json\r\n
    Object:
    [Path with value [truncated]: /token:eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjIsImxvZ2luIjoidXNlciIsInJvbGVzIjpbIlVTRVIiXSwiaWF0IjoxNjY0ODMxNjE1LCJleHAiOjE2NjQ4MzUyMTV9.ezO3By3TZEbYbnjz8mPSSWKHw7YRTMzxBMvOsJEDJwpCIdefIetbOfCdYIYU]

Client ---> Server2 (Запрос транзакций с помощью токена)
    GET /api/transactions HTTP/1.1\r\n
    Object:
     [truncated]Authorization: eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOjIsImxvZ2luIjoidXNlciIsInJvbGVzIjpbIlVTRVIiXSwiaWF0IjoxNjY0ODMxNjE1LCJleHAiOjE2NjQ4MzUyMTV9.ezO3By3TZEbYbnjz8mPSSWKHw7YRTMzxBMvOsJEDJwpCIdefIetbOfCdYIYUSEdIl7ebm

Server2  ---> Server3 (запрос транзацкии по id пользователя)
     GET /api/transactions HTTP/1.1\r\n
     X-Userid: 2\r\n

Server2 ---> Server4 (запрос транзацкии по id пользователя)
    GET /api/transactions HTTP/1.1\r\n
    Server2

Server4 ---> Server2 (получаем транзакции от сервера)
    HTTP/1.1 200 OK
    Content-Type: application/json

    {"transactions":[
    {"id":1,"userId":2,"category":"auto","amount":1000000,"created":1664831391},
    {"id":2,"userId":2,"category":"auto","amount":100000,"created":1664831391},
    {"id":3,"userId":2,"category":"food","amount":100000,"created":1664831391}],
    "categoryStats":{"auto":1100000,"food":100000}}

Server3 ---> Server2 (получаем транзакции от сервера)
    HTTP/1.1 200 OK
    Content-Type: application/json

    {"transactions":[
    {"id":1,"userId":2,"category":"auto","amount":1000000,"created":1664831391}
    ,{"id":2,"userId":2,"category":"auto","amount":100000,"created":1664831391}
    ,{"id":3,"userId":2,"category":"food","amount":100000,"created":1664831391}],
    "categoryStats":{"auto":1100000,"food":100000}}


Server2 ---> Client (получаем транзакции от сервера)
    HTTP/1.1 200 OK
    Content-Type: application/json

    {"transactions":[
    {"id":1,"userId":2,"category":"auto","amount":1000000,"created":1664831391}
    ,{"id":2,"userId":2,"category":"auto","amount":100000,"created":1664831391}
    ,{"id":3,"userId":2,"category":"food","amount":100000,"created":1664831391}],
    "categoryStats":{"auto":1100000,"food":100000}}
```

## Задание 2 Токен*

Я взял токен, декодировал его с Base64, получил строку:
```
{"alg":"RS256","typ":"JWT"}{"userId":2,"login":"user","roles":["USER"],"iat":1664917417,"exp":1664921017} ...
```

Это JSON Web Token. Токен делится на 3 части: header, payload, signature.
Первый сервер генерирует подпись с помощью приватного ключа, вставляет её в токен.
Второй сервер проверяет подпись из токена с помощью публичного ключа.



