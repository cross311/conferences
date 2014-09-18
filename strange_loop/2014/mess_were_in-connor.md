The Mess We're In
=================

Presenter: Joe Armstrong

Writer: [Connor Ross](http://twitter.com/otter311)

### Introduction

He has been programming since 1965, wow.  Talks about the history of computers and programmers from the first programmer Kilburn.


### Core Talk

A computer could boot in 60s in 1985 and today computers are X1000 times faster, but why do we not boot up in 60ms?

#### What Went Wrong

- Code even you cannot understand in a week, that you wrote
- Code with no specs
- Code that is shipped as soon as it runs
- Code with added features
- Code that is fast but super obscure and incorrect
- Code that is not beautiful
- Code written when you do not understand the problem

Legacy Code

- programmers who wrote the code are dead
- no specificatino
- written in archaic languages
- "it works"
- management thinks modifying legacy is cheaper

State X Event -> New State

Your 250GB SSD has more states then 2 to the 7633587786 universes has # of atoms

#### Failures

Stuff fails -> Deal with it

To handle failures you need more then one computers.

- Distributed computing
- Parallel computing
- Concurrent programming

    Systems should self-repair

Now programmers have no common language and cannot talk to ether other

Programming without an internet connectin is almost impossible these days

#### What do the laws of physics say

A cause must always proceed an event.  Two phase commits break the laws of physics.

#### What can we do

get rid of names, and just use hashes.....  merge all files that are similar or the same.  Get rid of copies of stuff.

