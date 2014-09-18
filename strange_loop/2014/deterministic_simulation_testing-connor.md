Deterministic Simulation Testing of Distributed Systems
=======================================================

Presenter: [Will Wilson](http://twitter.com/foundationdb)

Writer: [Connor Ross](https://twitter.com/otter311)

#### Introduction

Why simulation testing might make your life easier.  Debugging distrubted systems is bettern then stabbing your self in the eye.

Trying to make a timewarp network error happen by itself for debuging is IMPOSSIBLE.

Surface level problem is that distributed systems are not repeatable by themselves when trying to make them fail.

#### Solve problems

Started off by not making a database they wrote a simulation of a database.  Dont debug a database debug a simulation.

3 ingredients of a deterministic systems

- Single threaded pseudo concurrency
- Simulated implementation of all external communication
- Determinism


##### How

- Flow
- create sims of network, connection, file.
- broken machine

simulated disasters

- clogging
- swizzling
- nukes
- dumb sysadmin
- etc

How do you find more bugs per hour then all your customers running time all added together.

- Increase the number of things failing
- Speed up time
- Buggify
- Hurst Exponent: hardware failures are not independant of eachother

Can run 5 to 10 million simulation runs in a night.

#### Bad News

What they created broke debugging.  Only left printf.

Simulation could be wrong

- Not brutal enough
- Miss understand the contract of the system
- Sinkhole (network power supplies do not last very long)

