**[Challenge Link: 104_transformation](https://play.picoctf.org/practice/challenge/104)**
This python script will get you the flag
```python
with open("enc", "r") as f:
    data = f.read()

flag = ""
for i in data:
    val = ord(i)
    flag += chr(val >> 8 & 0b11111111) + chr(val & 0b11111111)

print(flag)

with open("flag", "w") as f:
    f.write(flag)
```
