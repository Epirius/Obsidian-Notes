aka
- edit distance
- sequence alignment

**given two strings `A` and `B`, how many "edits" must we do in order to make the strings equal.**

operations:
- delete a char from `A` or `B` - Cost 1
- delete a char from Both `A` and `B` (instead of changing the char in one) - Cost 1


```
edit("", S) = |S|
edit(S, "") = |S|
edit(As, Bs) = edit(A, B)
edit(A, B) = 1 + min (
	edit(A[:-1], B)
	edit(A, B[:-1])
	edit(A[:-1], B[:-1])
)
```
