[Задание](https://github.com/netology-code/ibdev-homeworks/tree/master/03_cicd)

## Решение

В первой версии программы truffleHog нашел приватные и симметричные ключи:

```
Date: 2021-01-21 07:08:16 
Hash: d3d5d23e9b64d4c74ca66526b953afa2036391a2 
Filepath: service/keys/private.key

Date: 2021-01-21 07:08:16 
Hash: d3d5d23e9b64d4c74ca66526b953afa2036391a2 
Filepath: service/keys/symmetric.key

Date: 2021-01-21 07:06:57 
Hash: 357116ea59d9d0d4cfe8bed75c09da0f3ee99b2a 
Filepath: service/keys/private.key

Date: 2021-01-21 07:06:57 
Hash: 357116ea59d9d0d4cfe8bed75c09da0f3ee99b2a 
Filepath: service/keys/symmetric.key
```

Во второй версии программы, которую почистили с помощью BFG Repo-Cleaner, эти ключи удалили.
Мне не хватает знаний, но следующий коммит выглядит подозрительным, так как в нем содержаться роли и какие-то хеши. Также, этот коммит не удален во второй версии программы.

```
Reason: High Entropy
Date: 2021-01-21 07:06:57
Hash: 357116ea59d9d0d4cfe8bed75c09da0f3ee99b2a
Filepath: service/docker-entrypoint-initdb.d/01_data.sql
Branch: origin/master
Commit: feat(service): symmetric version added
                                                                                                  
@@ -1,4 +0,0 @@
-INSERT INTO users(login, password, roles)
-VALUES
-       ('admin', '$2a$10$ctPFhgJh.YIE21AA0OGl5er3p9f3XsAwkmTXnP2I7BxCpQbr1QAg2', '{"ADMIN", "USER"}'), -- у этого пользователя две роли (т.е. он и админ, и обычный юзер)
-       ('user', '$2a$10$ctPFhgJh.YIE21AA0OGl5er3p9f3XsAwkmTXnP2I7BxCpQbr1QAg2', '{"USER"}');
```

## Чтобы передать файл с помощью netcat:
ip a show на нашем хосте. Выясняем адрес на интерфейсе докера. В моем случае это 172.17.0.1. Затем на нашей основной машине nc -l -p 13080 > log.txt, а в контейнере докера nc -w 3 172.17.0.1 13080 < log.txt

