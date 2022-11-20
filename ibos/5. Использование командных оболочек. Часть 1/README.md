[Задание](https://github.com/netology-code/ibos-homeworks/tree/v2/05_shell)

```bash
#!/bin/bash -
echo $11
```


```bash
#!/bin/bash -
((v=1+$1))
echo $v
```


```bash
#!/bin/bash -
for x in $(ls)
do 
	echo $x
	((z=z+1))
done
echo 'Files in directory: '$z
```


```bash
#!/bin/bash

if [ -e $1 ]
then
	echo 'file exist'
else
	echo 'file didnt exist'
fi


if [ -d $1 ]
then
	echo 'this is directory'
fi


if [ -f $1 ]
then
	echo 'this is file'
fi


```


```bash
#!/bin/bash -


if (($# != 2))
then
	echo 'Allow only 2 arguments'
	exit 1
fi
if [[ $1 != crypt ]] && [[ $1 != decrypt ]]
then
	echo First argument must be crypt or decrypt
	exit 2
fi
if [ $1 == crypt ]
then
	echo 'Encrypting...'
	echo $2 | base64
fi
if [ $1 == decrypt ]
then 
	echo 'Decrypting...'
	echo $2 | base64 -d
fi
```