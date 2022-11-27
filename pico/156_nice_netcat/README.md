First just run the netcat command and store the output in a file
```
$ nc mercury.picoctf.net 21135 > ncout
```

Now just use the following python script to get the flag out of it
```python
with open("ncout", 'r') as f:
    data = f.read()

data = data.split()
flag = ""

for i in data:
    flag += chr(int(i))

print(flag)

with open("flag", 'w') as f:
    f.write(flag)
```
