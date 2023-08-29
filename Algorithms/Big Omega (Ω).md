
Big Omega lower bounds the given function
#### Def (Omega) 
```
f(n) is Ω(g(n)) if there exists some n0 >= 0, c > 0
such that for n > n0
f(n) >= c g(n)
```

```
f(n) = p n^2 + q n + r
>= p n^2

let c = p
then for all n > 0
fn >= c n^2

f(n) = Ω(n^2)
but also Ω(n)
```