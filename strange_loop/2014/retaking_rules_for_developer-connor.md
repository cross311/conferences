Retaking Rules For Developers
=============================

Presenter: [Ryan Brush](http://twitter.com/ryanbrush)

Writer: [Connor Ross](http://twitter.com/otter311)

### Introduction

Slogger -> Social Logger. Connor look this up.

Starting off with a story.  Looking at 1977 when computers where slow and hard to program.

If knowledge is the most important thing?  How do we split the code to business logic gap?

Charles Forgy.  

```

Hypertension (severity == moderate)
  -> recommend-diet-changes


Hypertension (severity == moderate)
Demographics(age > 60)
  -> prescribe-bp-meds

```

Codified knownledge and how to map them to other things.  Rules engines.  symbolic lisp machines.

http://en.wikipedia.com/Hype_cycle

### Core

Wanted: System that can produce code without requiring coders

```

rule "My Rule"
 When "This"
 Then "That"

```

Tools targeted business uses not developers.  for simple problems greate.

Rule Authoriing is development whether we all it that or not.  What if we approach expert systems as code.


Easy to make functions that take in and output. but putting them together becomes a mess.  Explicit wireing is complete and error prone.  Can we automatically wire them up?

Every function defines a type, given a contraint returns a type or action.  Rules as a control structure.

Tools

- Nools (javascript)
- Wongi (Ruby)
- Clara (clojure)

Clojure

- data over objects
- equality means something
- Reach
- Can grow the language
- hello, macros

#### Demos

