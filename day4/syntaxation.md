Syntaxation
===

Presentor: Douglas Crockford

## The Thought of Syntax

Syntax is the least important aspect of programming language design.  But this is like the same thing of saying Fashion is hte least important aspect of clothing design.  The first part of fashion is to protect you from the sun or the ground, bu sometimes that is not always true right.  People make and buy shoes that hurt their feet not protect them.

Now people are writing langauges just to compile into javascript, it is all about the syntax not about the language.

## if statement

Fortran if statements where really really ugly and used goto methods.

Algol 60: uses blocks begin and end.  First language to not use only the = sign for assignment, A:=B

BCPL: Used brackets instead of begin and end.

B: Smaller version of BCPL, brought the equal for assignment and equality.  also brought back params.

ADA: Implied blocks, using end if. then later it because if -> fi.

## Parsing

Parsing tends to drive how a language ends up being in its final syntax.

Top Down Operator Precendence =>  have you ever heard of this??  Even if you took a parsing class, they dont even teach it.  The author of it even said that he would be overlooked.  The presentor says that this parsing technique is the most beautiful and best he has ever seen.  Requires a function programming language.

What do we expext to see to the left of the token: left denotation or null denotation.

Tokens are objects: prototype <- symbol <- token  functions( advanced(), advance(id))

goes through how we would actually write the objects for what i just described.

## Advice for language designers

We cannot do our work with out languages.  Presentor thinks that everyone should be writing their own langauges.  This allows you on eunderstand what languages are doing.

Embrace minimalism -> find the ideal solution for one specific problem, dont solve everyting at once.  Keep the notation minimal but dont make it cryptic.  Make it readable, it must be quickly undertood when it is read.  Error resistant, eliminate confusion.

Innovate -> we already have enough java like language. select you feature carefully.  beware of sometimes useful, this means not useful.  manage complexity, let the program be complex not hte language.  make new mistakes, dont make mistakes that already exist.  

Syntax you really dont want it, but you need it and in the end you love it.