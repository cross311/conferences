Deterministic Simulation Testing of Distributed Systems
==========================================================
Presentor: Will Wilson
Author: Dan Hoizner

Testing distributed systems is horrible (but preferable to sticking a fork in your eye).
Repeatability? Yea, right.

Reproducing bugs in distributed systems is hard. Dependant on network conditions, which you might never be able to reproduce on your machine...but it will happen on a client. Once you've fixed the bug, how do you verify that you actually killed it for good?

Lack of repeatability is a special case of non-determinism.
Send two packets....A gets lost in a time-warp and B shows up first. The machine being contacted assumes an order of A, then B. Good luck!

FoundationDB is a distributed stateful system with ridiculously strong guarantees. **ACID!**

*Don't debug your system, debug a simulation instead.*

##3 ingredients of deterministic simulation

1. Single-threaded pseudo-concurrency
2. Simulated implementation of all external communication
3. Determinism

###Single-threaded pseudo-concurrency
**Flow**

A syntastic extension to C++, new keywords and actors, "compiled" down to regular C++ w/callbacks.

###Simulated Implementation
Interfaces, ahoy!

* INetwork -> SimNetwork
* etc

Latency, peer closed, connection failed.

###Determinism

We have (1) and (2), so all we need to add is none of the control flow of anything in your program depending on anything outside of your program + its inputs.

Use unseeds to figure out whether what happened was deterministicc

1+2+3 == **The Simulator**

###The Simulator

* Set of goals for the system
* Set of deterrents

####Types of disasters:

* broken machine
* clogging
* swizzling
* nukes
* dumb sysadmin
* etc

You are looking for bugs... the universe is also looking for bugs.
How can you make your CPU more efficient than the universe's?

1. Disasters here happen more frequently than in the real world.
2. Speed up time
3. Buggify!
4. The Hurst exponent
  Hardware failures are **NOT** independent events.

#Takeaways
* We're run the equivalent of *trillions of hours* of "real world" tests.
* We broke debugging (but at least it's possible).
* What if the simulation is wrong?
  - It is not brutal enough.
  - We misunderstood the contract of the operating systmes.
* Backup cluster: **Sinkhole**: simulates power surges, etc.
* Two "bugs" found by Sinkhole:
  - Power safety bug in ZooKeeper
  - Linux package managers writing conf files don't sync

#Future Directions

1. Dedicated "red team"
2. More hardware
3. Try to catch bugs that "evolve"
4. More real world testing
