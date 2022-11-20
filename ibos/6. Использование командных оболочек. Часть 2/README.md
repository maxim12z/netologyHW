[Задание](https://github.com/netology-code/ibos-homeworks/tree/v2/06_shell)

```powershell
Write-Host "Add string 1" -ForegroundColor Green
$s=1
$n=7
Write-Host $n$s
```

```powershell
Write-Host "Add number 1" -ForegroundColor Green
$n=7
$n+1
```

```powershell
Write-Host "Print list of files and its number" -ForegroundColor Green
$ls=ls
$m=0
foreach($n in $ls)
{
	Write-Host $n
	$m += 1
}
Write-Host "Number of files: " $m 
```

```powershell
Write-Host "File, Directory or NotExist" -ForegroundColor Green
if(Test-Path -Path $args[0])
{$a="File exist"}

if(Test-Path -PathType Container -Path $args[0])
{$b=" and its Directory"}

if(Test-Path -PathType Leaf -Path $args[0])
{$b=" and its File"}

Write-Host $a$b -ForegroundColor Green
```

```powershell
if($args.Count -ne 2)
{
Write-Host 'Allow only 2 arguments' -ForegroundColor Yellow 
exit 1
}
#$LASTEXITCODE

if($args[0] -ne 'crypt')
{
if($args[0] -ne 'decrypt')
{
Write-Host 'First argument must be crypt or decrypt' -ForegroundColor Yellow
exit 2
}
}

if($args[0] -ne 'decrypt')
{
if($args[0] -ne 'crypt')
{
Write-Host 'First argument must be crypt or decrypt' -ForegroundColor Yellow
exit 2
}
}

if($args[0] -eq 'crypt')
{
$cr=[Convert]::ToBase64String([System.Text.Encoding]::UTF8.GetBytes($args[1]))
Write-Host 'Encrypting'
Write-Host $cr -ForegroundColor Green
}
if($args[0] -eq 'decrypt')
{
$cr=[Text.Encoding]::Utf8.GetString([Convert]::FromBase64String($args[1]))
Write-Host 'Decrypting'
Write-Host $cr -ForegroundColor Green
}
```