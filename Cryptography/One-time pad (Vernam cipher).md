#historic 
the one-time pad is a version of the [[Vigenere cipher]] that is provably secure. it archives this by having a key as long as your message, such that there will be no repetition in the cipher text.

you can not apply [[cryptographic frequency analysis]] since the key does not repeat.

it is provably unbreakable provided some conditions are met:
- they key is truly random (not just [[Random Number Generators|pseudo random]])
- they key must never be reused, if it is used to encrypt two different messages, it is no longer secure.

it is secure because the cipher text can be decrypted to any word with the same number of letters when brute forcing the key.

The problem with this method is generating and distributing the random keys, so it is not practical. but as opposed to modern encryption methods which can be broken given enough time and resources, this is provably secure.