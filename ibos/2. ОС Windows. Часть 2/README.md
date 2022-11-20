[Задание](https://github.com/netology-code/ibos-homeworks/tree/master/02_win)

### 1. Для каких пользователей (логины и SID'ы) зарегистрированы события типа Audit Failure (в русскоязычной Windows - Аудит отказа) по доступу к файлу Share.txt?

```
Account Name: anonymous
SID 1003
Account Name: teacher
SID 1001
```

### 2. Каковы ID событий (Event ID) и время, когда это было зафиксировано (в русскоязычной Windows Код события)?

```
Event ID 4656
11/10/2020 2:52:45 AM пользователь anonymous
11/10/2020 2:52:24 AM пользователь teacher
```

### 3. С помощью каких процессов (приложений) была осуществлена попытка доступа (в русскоязычной Windows Имя процесса)?

```
Process Name: C:\Windows\System32\notepad.exe
```
