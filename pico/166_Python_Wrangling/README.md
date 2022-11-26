Run following to get the flag
```sh
cat pw.txt | xargs python ende.py -d flag.txt.en > flag
```
Or Run following
```sh
$ cat pw.txt
ac9bd0ffac9bd0ffac9bd0ffac9bd0ff
$ python ende.py -d flag.txt.en
Please enter the password:ac9bd0ffac9bd0ffac9bd0ffac9bd0ff
picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}
```

**Note** Always use 32 charater for Ferent, less or more than that will get ValueError
```py
from cryptography.fernet import Fernet
import base64

passkey = input("Enter the passkey (Enter exact 32 characters): ")
b64 = base64.urlsafe_b64encode(passkey.encode())
crypt = Fernet(b64)
```
