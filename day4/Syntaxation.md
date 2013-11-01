# Syntaxation
#### Douglas Crockford Keynote, Wednesday 8:30-9:30

> "I say 'jason' -- you can say it however you want."

### Introduction
- JavaScript is now the universal Virtual Machine
 - Hundreds of languages being translated into JavaScript
 - Many new languages designed to become JavaScript
 - JSLint is a subset of JavaScript; "not nearly as crappy."
- Syntax is the least important aspect of language design, in the same sense that fashion is the least important aspect of clothing design.

### Some History
- FORTRAN IV: Introduced IF statement; whitespace ignored, use for parens
- BCPL: Subset of CPL; first "curly brace" language; := for assignment
- Ada: -- comments, implied blocks, end if, :=
- Algol 68: cent signs for comments!, 'fi' for end if.

### Emotional Style: Fashionable Tolerance of Syntactic Ambiguity
- Operator precedence or binding power; ambiguous compared to simple left-to-right or right-to-left evaluation. Instead, you have to memorize a whole list of operator precedence in each language!
- Use of words. Variable? Statement keyword Operator? Special form?
- Parentheses overload: Function definition and invocation, grouping, separation.

### Top Down Operator Precedence (1973)
- Simple, flexible, easy to use, beautiful.
- Why have you never heard of it?
 - Preoccupation with BNF grammars
 - Requires a functional programming language.
 - LISP community did not want syntax.
 - JavaScript is a funcional language with a community that likes syntax.
- What do we expect to see to the left of the token?
 - left denotation (led) and null denotation (nud)
 - tokens are objects: prototype <-- symbol <-- token 
- Easy to build parsers: very little code, does almost nothing, fast enough to use as an interpreter, no more reserved words, and extensible language

### Advice for language designers
> "Everybody in this profession should be designing their own languages all the time"

- Minimalism
 - Conceptual
 - Notational - don't be cryptic
 - Readable - Can be easily and correctly understood by a reader
 - Error resistant - confusion free
- Innovate
 - We already have many Java-like languages
 - Select your features carefully. 
 - Beware of Sometimes Useful
 - Avoid universality
 - Manage complexity
 - Promote quality
 - Make new mistakes
 - Leap forward
 - Let the language teach you.
 - Embrace Unicode
 - Forgotten treasures: State machines, constraint engines.
 - Exploit parallelism.
 - Distributed programming: clouds and cores.
 - Have fun.
 
https://github.com/douglascrockford/TDOP

https://github.com/douglascrockford/JSLint

Beautiful Code: Leading Programmers Explain How They Think. 