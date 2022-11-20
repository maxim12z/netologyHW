[Задание](https://github.com/netology-code/ibos-homeworks/tree/v2/09_python3)

```python
import hashlib
from Crypto.Cipher import AES
from Crypto import Random

BS = AES.block_size
pad = lambda s: s + (BS - len(s) % BS) * chr(BS - len(s) % BS)
unpad = lambda s : s[:-ord(s[len(s)-1:])]

key = '123'
key = key.encode("UTF-8")
key = hashlib.sha256(key).digest()

def crypt(plain_text):
    print("Plaint text: ", plain_text)
    plain_text = pad(plain_text)
    iv = Random.new().read(BS)
    cipher = AES.new(key, AES.MODE_CBC, iv)
    cipher_text = (iv + cipher.encrypt(plain_text.encode()))
    print("Ciphered text: ", cipher_text.hex())
    return cipher_text

def decryptd(cipher_text, key):
    iv = cipher_text[:BS]
    cipher = AES.new(key, AES.MODE_CBC, iv )
    plain_text = unpad(cipher.decrypt(cipher_text[BS:]))
    return plain_text

cipher_text = crypt('netology , secret')

set_a = set()
for elements in range(100,1000):
    elements = str(elements)
    bf_key = elements.encode("UTF-8")
    bf_key = hashlib.sha256(bf_key).digest()
    if decryptd(cipher_text, bf_key) != b'':
        try:
            kkk = decryptd(cipher_text, bf_key).decode("UTF-8")
            set_a.add(kkk)
        except UnicodeError:
            pass
for elements in set_a:
    print(elements)


```