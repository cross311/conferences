Coder Decoder: Functional Programming
======================================
Presentor: [Katie Miller](@codemiller)
Author: [Dan Hoizner](https://github.com/dhoizner)

#No one can be told what the Monad is...

Functional Programming concepts, not Haskell concepts.

```
list1 = [1,2,3] --immutable
list2 = [4,5,6]

list1 ++ list2 --concat
catcon list1 list2 --function call

catcon :: [Int] -> [Int] -> [Int]

catcon :: Num a => [a] -> [a] -> [a]

catcon :: [a] -> [a] -> [a]

catcon xs ys = ys ++ xs
```

OpenShift PaaS by Red Hat

* Referential Transparency
```
score = succ (2+3)
main = putStrLn (show score)
```

* Higher-Order Functions - WHAT: a function that takes a function as an argument or returns one as a result, WHY: glue pieces of code together; reduce code repetition; modular design

```
let list1 = [1,2,3]
:type map

map :: (a -> b) -> [a] -> [b]
```

* Currying: WHAT: evaluating multi-argument functions as a chain of functions that each take exactly one argument, WHY: aids code reuse; can make code more readable

```
catcon :: [a] -> [a] -> [a]
catcon xs ys = ys ++ xs

:type catcon [1,2,3]
catcon [1,2,3] :: Num a => [a] -> [a]
```

* Closures: WHAT: an instance of a function together with the environment in which it was created, WHY: make app code more concise

```
(\ch n -> (\str -> take n (repeat ch) ++ str)) 'a' 5 "ha"
"aaaaha"
```

* Functor: WHAT: structure that can be mapped over, WHY: use abstraction to reduce repeated code
```
fmap reverse getLine
```

* Monad: WHAT: structure that puts values in a computational context and implements functions that facilitate the chaining of these computations, WHY: a large number of very useful functions can be written once for any type that fits the pattern
```
["walk", "nap", "fight"] >>= (\t -> return ("cat" ++ t))
```

* Lens: WHAT: data structure for accessing and mutating values in a data type, WHY: provides concise, functional way of drilling down into data types to get or set

* Learn you Haskell for Great Good.

#Resources
[Coder Decoder](http://decoder.codemiller.com)
