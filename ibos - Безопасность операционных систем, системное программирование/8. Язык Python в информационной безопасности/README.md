[Задание](https://github.com/netology-code/ibos-homeworks/tree/v2/08_python2)

```python
import nmap3
nmap = nmap3.Nmap()
#dir(nmap3)
#help(nmap3.Nmap)
version_result = nmap.nmap_version_detection('10.0.2.16')
res = version_result['10.0.2.16']['ports']
Num = 0
print('Scan result: ')
for elements in res:
    Num += 1
    print(f'{Num} Protocol: {elements.get("service").get("name")}; Version: {elements.get("service").get("product")}, {elements.get("service").get("version")}; Open port: {elements.get("portid")}')
```
