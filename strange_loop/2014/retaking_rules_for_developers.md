Retaking Rules for Developers
================================
* Intelligent systems derive their power from the *knowledge they possess* rather than the specific ... feigenbaum
* mind the gap
    - domain knowledge
    - what the code looks like
* Composable units of knowledge
* Instead of running all the rules against all the data, build a commonality graph and only run the applicable rules in order.
    - Charles Forgy
    - NASA!
* "Frankly, there were a lot of intellectually dishonest promises made." - Peter Gabel, *Bring in the Expert*
* The AI Winter
    - [Hype Cycle](http://en.wikipedia.org/wiki/Hype_cycle)
* A Wrong Turn
    - IT employment level shoots up
    - A system that can produce code without requiring coders

```
rule "My Rule"
  when: This
  then: That
```

* Often the central pitch for a rules engine is that ... - Martin Fowler
* Tools target business users
    - great for simple problems
    - but wait... problems don't stay simple

```
rule "My Rule"
  when:
    // Pile of Java code
  then:
    // Pile of Java code
```

* Rule authoring is development, whether we call it that or not.
* So let's approach expert systems as code

```
A B
f(A,B) => C
g(B,C) => D
h(A,C,D) => E
```

* wire everything together...EEK!

##Rules as a Control Structure:
```
unit-of-logic
  Type[constraints]
  Type[constraints]
 =>
  action
```

##A Principled Design:

* Start with a proven model
* Facts -> Working Memory -> match facts -> knowledge base -> infer facts -> working memory
* Unification
* Truth maintenance
    - if A assert B
    - if !A retract B

#Systems
* Nools (JS)
* Wongi (Ruby)
* Clara (Clojure)

#Why Clojure?
* Data over objects
* equality means something
* reach
* can grow the language
    - (Hello, macros!)

#A new role for rules
* a tool for developers
* a means to minimize the semantic gap
* leverage for a shared understanding

#Just don't write JAVA code in Excel
engineering.cerner.com
github.com/rbrush/clara-rules
