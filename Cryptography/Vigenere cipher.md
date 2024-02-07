#historic 

the [[Mono-alphabetic substitution cipher]] always encrypts the same plain text letter to the same cipher text letter, making it vulnerable to [[cryptographic frequency analysis]].

The Vigenere cipher shifts plain text letters (like [[Caesar cipher]]) but by different amounts for each letter. this avoids the [[cryptographic frequency analysis]].

the key for Vigenere is a sequence of numbers for how much a letter should be shifted by, and you index into this list based on the position of the plain text letter. you can repeat the pattern if your plain text is longer then the key.
the key can be represented by letter, and it can therefore be a word which is easier to remember.

The Vigenere is the same as the [[Caesar cipher]] if the key is of length 1.

 it is vulnerable to to [[cryptographic frequency analysis]] if you know the length of they key, which you can guess if the same word is repeated in the message multiple times in such a way that the repeating key encrypts the same word to the same cipher text