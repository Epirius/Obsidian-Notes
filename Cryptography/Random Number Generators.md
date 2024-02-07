we distinguish between 3 types of RNG's

## true random number generators
- flipping a coin, atomic measure of alpha particles etc..
- true random number stems from random physical processes

## pseudo random number generators (prng)
- not really random
- pseudo random numbers are computed, i.e. they are deterministic. and can be recreated if you know the seed 
- they are often computed with the following function.
```
s0 = seed
s(i + 1) = f(si)
```

## cryptographycally secure prng's (cprng)
cprng's are prng's with an adittional property:
- the numbers are unpredictable. given n output bits  