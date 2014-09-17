Node.js Now!
============
Presenter: [Dan Shaw](https://twitter.com/dshaw)
Writer: [Connor Ross](https://twitter.com/otter311)

Introduced as having something to do with [NodeBots](http://nodebots.io/)

## Introduction

How is node being used now, how will it be used inthe next 5 to 10 years.

Presenter is host of pdcast: NodeUp.  Helped create NodeBots Day and NodeBots SF.  

## Main Content

Javascript became a really strong option when V8 engine came into being.  Given todays ability to view the internet on mobile devices and even on tvs, the amount of information you can pipe to a device is getting smaller again.  Nodejs helps to small streams open to just send the data that needs to be sent when it needs to be sent.


Javascript is starting to become more of a core language for arduino and other embeded devices.

The ability to rapidly take an idea and create an applicatin is super fast, compared to something like Java.  Could deploy a javascript applicatin into productoin with in minutes, and cycle changes just as fast.  Went as far to say that by 2014 javascritp will be the most in-demand language skill in application development.

### 2009

Node js released.  A framework to more effectivly create applications.

### 2010

People begin to adopt node. Many different package managers, and things were kinda messy.  The community decided to go with one package manager to rule them all, NPM.

### 2011

NodeJs now has the ability to work everywhere.  Windows, OSX, Linux. 

### 2012

All things REALTIME.  socket.io comes along.  Saying Boxer is pushing node.

### 2013

Enterprise enters the nodejs world.  Walmart and paypal.  Walmart team deployed a nodejs mobile backend for black friday.  They even redeployed during th eday just to see if anythign would go bad.

### 2014

Node is now used large scale.  Very big applications are beign built in nodejs.  Netflix, ...


### The Challenge Of NodeJs

Monolithic systems, that are large, behind schedle, super intermingled.  

    SHIPPING CODE WINS
    - Dan Shaw

A lightweight front end teir that is written in a language they understand will empor them to make their own changes.  Separate concerns, that allow front end to change at a rapid pace, while the backend services change slowly.  Avoid the context switch from front-end javascript and backend c# | java | c.

### API OR DIE

Have your front end talk to apis not to a database.  Systems begin to look like a series of proxies.  Presenter is saying that if you start to notice your system start to look like a system of proxies you are doing it write.  The amount of lag in nominal compared to the ability to break apart concerns.

### Test Early Test Often

Goes over normal reasons to test.

### Automate Everything

Your job is to write business logic not common tasks.  If you dont want to do it all the time, automate it!

## END
