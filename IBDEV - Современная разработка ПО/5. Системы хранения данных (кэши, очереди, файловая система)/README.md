[Задание](https://github.com/netology-code/ibdev-homeworks/tree/master/05_storage)

## Задание Redis ACL
```
1.
127.0.0.1:6379> ACL WHOAMI
(error) NOAUTH Authentication required.
127.0.0.1:6379> ACL LIST
(error) NOAUTH Authentication required.
127.0.0.1:6379> AUTH default
(error) WRONGPASS invalid username-password pair or user is disabled.

2.
127.0.0.1:6379> AUTH app secret
OK
127.0.0.1:6379> ACL WHOAMI
(error) NOPERM this user has no permissions to run the 'acl' command or its subcommand
127.0.0.1:6379> ACL LIST
(error) NOPERM this user has no permissions to run the 'acl' command or its subcommand
127.0.0.1:6379> SET users:admin@localhost id:1|name:vasya
OK

3.
127.0.0.1:6379> ACL WHOAMI
"default"
127.0.0.1:6379> ACL LIST
1) "user app on #2bb80d537b1da3e38bd30361aa855686bde0eacd7162fef6a25fe97bf527a25b ~* &* -@all +@write +@read"
2) "user default on nopass ~* &* +@all"
127.0.0.1:6379> SET users:admin@localhost id:1|name:vasya
OK
```


## Задание Redis ACL LOGS
```
127.0.0.1:6379> acl log
1)  1) "count"
    2) (integer) 1
    3) "reason"
    4) "command"
    5) "context"
    6) "toplevel"
    7) "object"
    8) "acl"
    9) "username"
   10) "app"
   11) "age-seconds"
   12) "16.486000000000001"
   13) "client-info"
   14) "id=3 addr=127.0.0.1:48570 laddr=127.0.0.1:6379 fd=7 name= age=471 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=22 qbuf-free=40932 argv-mem=6 obl=0 oll=0 omem=0 tot-mem=61462 events=r cmd=acl user=app redir=-1"
2)  1) "count"
    2) (integer) 3
    3) "reason"
    4) "auth"
    5) "context"
    6) "toplevel"
    7) "object"
    8) "auth"
    9) "username"
   10) "default"
   11) "age-seconds"
   12) "39.256"
   13) "client-info"
   14) "id=3 addr=127.0.0.1:48570 laddr=127.0.0.1:6379 fd=7 name= age=449 idle=0 flags=N db=0 sub=0 psub=0 multi=-1 qbuf=23 qbuf-free=40931 argv-mem=7 obl=0 oll=0 omem=0 tot-mem=61463 events=r cmd=auth user=default redir=-1"
127.0.0.1:6379> 

```