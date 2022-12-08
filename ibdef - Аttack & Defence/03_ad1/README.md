# Домашнее задание к занятию «Active Directory. Часть 1»
[Ссылка на задание](https://github.com/netology-code/ibdef-homeworks/tree/master/03_ad1)

## Задание 1
Описываю порядок действий 
1. Настроил сеть на виртуальной машине 
2. Настраиваю требуемые роли на сервере
![data/Server-Roles.png](data/Server-Roles.png)
![data/Server-Roles2.png](data/Server-Roles2.png)
3. Настраиваю контроллер домена Active Directory
![data/DS-conf.png](data/DS-conf.png)
![data/DS-conf2.png](data/DS-conf2.png "data/DS-conf2.png")
4.Заканчиваю настройку служб DHCP DNS
![data/DHCP.png](data/DHCP.png)
## Задание 2
1. Создаю пользователей.
![data/student1.png](data/student1.png)
![data/student2.png](data/student2.png)
2. Создаю группы
![data/students1.png](data/students1.png)
![data/students2.png](data/students2.png)
3. Добавляю студента 1 в группу
![data/group-add.png](data/group-add.png "data/group-add.png")
4. Добавляю студента 2 в группу
![data/group-add2.png](data/group-add2.png "data/group-add2.png")
## Задание 3
Добавляю вторую виртуальную машину в домен
![domain-change.png](data/domain-change.png)
![domain-change2.png](data/domain-change2.png)

Захожу под доменными учетными записями
![login1.png](data/login1.png)
![login2.png](data/login2.png)


## Задание 4
1. Добавляю новую груповую политику для студента1
![4-0.png](data/4-0.png)
2. Логинюсь на виртуальной машине, видно что пункт "Выключение" исчез
![4-1.png](data/4-1.png)
3. Удаляю групповую политику
![4-2.png](data/4-2.png)
4. Логинюсь снова, пункт "Выключение" снова появился
![4-3.png](data/4-3.png)
