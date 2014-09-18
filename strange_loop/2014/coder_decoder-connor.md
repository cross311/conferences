Coder Decoder
=============

Functional Programmer Lingo Explained, with Pictures
--------

Presenter: [Katie Miller](http://twitter.com/codermiller)

Writer: [Connor Ross](http://twitter.com/otter311)

### Introduction

OpenShift Developer Advocate at Red Hat

Starts off with a poem of functional programming terms.

### Core Talk

Using haskell.  But all concetps can be applied accross languages.

```

list1 = [1,2,3]
list2 = [4,5,6]

list1 ++ list2
-- [1,2,3,4,5,6]

catcon list1 list2
-- [4,5,6,1,2,3]

catcon :: [a] -> [a] -> [a]
catcon xs ys = ys ++ xs

```

- Refrential Transparency
- Higher-Order Function
- Currying
- Closure
- Functor
- Monad
- Lens

