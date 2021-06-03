We are given the code `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])` and the ciphertext `灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸強㕤㐸㤸扽`

Looking at the code I thought that it is changing the encoding by shifting it to the left by 8bits which probably means the ciphertext is in utf-8

To undo this I tried encoding it to utf-16, which got close but did not give the flag
```
>>> c.encode('utf-16')
b'\xff\xfeipocTC{F61b_ti_snits43_dfo8_7_d58489}b'
```
Then I tried encoding it with big-endian byte serialization which gave the flag
```
>>> c.encode('utf-16-be')
b'picoCTF{16_bits_inst34d_of_8_75d4898b}'
```
Flag: `picoCTF{16_bits_inst34d_of_8_75d4898b`  
