as opposed to a [[Block cipher]], a stream cipher works on individual bytes. 

They take a byte and xor it with a keystream byte. where each bit in the byte is xor'd

the keystream has to be the same for encryption and decryption making it [[symmetric encryption]]

```
example: 
encryption:
plaintext:  1000001
keystream:  1011001
ciphertext: 0011000

decryption:
ciphertext: 0011000
keystream:  1011001
plaintext:  1000001
```

the keystream has to generated from a [[Random Number Generators]]