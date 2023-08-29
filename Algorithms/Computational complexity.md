We have mentioned time complexity, but we can also analyse the computational resources used by an algorithm, such as: 
- memory (space)
- power usage
- bandwidth
- time
- [[lock|locks]]
- file handles
- etc

Develop a mathematical theory of complexity.
in general, time is always >= space, other resources.
hence we will focus on time complexity.
We don't run out of time, but we do run out of space.

We analyse the performance of an algorithm with regards to the size of its input.

## What is an efficient algorithm
In inf 234 we focus on the worst case complexity, but you could also analyse the expected running time.

#### [[Big O]]  - F <= O
big O ignores constants, and smaller terms.
it therefore upper bounds the given function.

#### [[Big Omega (Ω)]] - F >= Ω
Big Omega lower bounds the given function

#### [[Big Theta (Θ)]] - F >= Θ and F <= Θ
Big theta is a combination of Big O and Big Omega


sum (+)
- O(n)
- Ω(n)
- Θ(n)

product (x)
- O(n^2)
- Ω(n)
- Θ(?)