[Задание](https://github.com/netology-code/ibos-homeworks/tree/master/01_win)

### Какой процесс отображается в логе первым? Какой у него PID? 

System. PID 4

### Какой "драйвер" загружается первым? Что это за драйвер (ответьте своими словами)? 

C:\Windows\System32\Drivers\PROCMON24.SYS

Это как раз Process Monitor, который записывает лог загрузки. 

### Какой PID у родительского процесса для smss.exe (не у самого smss.exe, а у того, кто его создал)? 

Parent PID 0

### Какой процесс является родительским для процесса winlogon.exe? Где расположен файл winlogon.exe? 

Parent PID 444 (Windows Session Manager smss.exe)

C:\Windows\system32\
### Какой процесс является родительским для процесса lsass.exe? 

Parrent PID 452 (Windows Start-Up Application wininit.exe)

### Что будет если в таск менеджере (taskmgr.exe) завершить работу следующего процесса: 

Система «разлогинивается». Т.е. пользователя выбрасывает в окно с введением логина и пароля. 


