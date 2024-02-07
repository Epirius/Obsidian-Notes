#historic 
The key is short, usually a word, that is expanded into a longer key.
we start by removing repeating letters from they key.
the letters are then placed in a 5x5 grid, with the remaining letters of the alphabet added afterwords.

i = j in this grid since 5x5 = 25 and there are 26 letters in the alphabet.

the plain text is split into pairs of letters, and an X is added to the message if the number of letters are odd. encryption proceeds pair by pair.
if the pair are on the same row in the 5x5 grid, you shift to the right, if they are in the same column you shift down. otherwise swap their columns.

![[Pasted image 20240207131855.png]]
if the pair of letters are the same, you swap the second letter with an x

to decrypt you just reverse the rules for encryption.

## issues
it is insecure for the same reason the [[Mono-alphabetic substitution cipher]] was insecure. a pair of letters will always swap to the same pair of letters, making it vulnerable to [[cryptographic frequency analysis]] on pairs of letters.

a given letter can only encrypt to 5 other letters.

unless the keyword is very long, the lower half of the 5x5 grid becomes predictable.