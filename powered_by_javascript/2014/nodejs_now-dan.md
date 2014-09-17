Node.js Now!
============
Presenter: Dan Shaw
Writer: Dan Hoizner

# Context for Node.js in JavaScript
* Programming in JavaScript on the server.
  - available since 1998 (?) (Netscape-ish?)
* V8 made server-side JS viable.
* The days of Flash are over (!!).
* Mobile/Desktop/TV all need different server makeup.
  - Mobile - want to keep the data pipe open

# Internet of Things
* Creating rich experiences (for ourselves) with the devices around us is compelling
  - **not** Nest saying: *Your house is on fire, you should probably look for a new house*.
* Nodebots -> program Arduino/hardware using JS rather than C-dialects and lower.

# Why JavaScript?
* JavaScript -> An approachable pervasive language that powers all platforms.
* Rapid cycle time from ideation to implementation (rapid prototyping).
* "By 2017, JavaScript will be the most in-demand language skill in application development." - Forrester Research 2014

# Node
* Designed as a systems language.
* (2010) Early adopters.
  - messy
  - many ineffective package managers
  - modules were broken and messy
* (2011) - Node 6
  - Full cross-platform availability
  - It works! (everywhere!)
  - Huge investment by microsoft
* (2012) - REALTIME ALL THE THINGS!
  - socket.io
  - Boxer
* (2013) - Enterprise proof
  - Walmart - mobile traffic on Node.js
    - Re-deployed in the middle of Black Friday
  - PayPal (JAVA -> Node.js)
* (2014) - Large Scale Node.js
  - Netflix, et. al.

# The Engineering Challenge
* Monoliths
  - API + front-end logic causes tension and slow-down
  - RAILS
  - 6 months to 24 months behind schedule
* Shipping code wins all

# The Frontend Backend
* Backend services <--> Node.js Frontend Backend <--> HTML5 Frontend experience
* frontend team -> frontline of customer experience
* Separation of concerns
  - backend evolves slowly
  - frontend assets are constantly changing
* Avoid excessive abstraction
* CSS in C++ and JAVA.... ICK!
* Avoid context switching
* API OR DIE
* DATABASES MUST DIE
* It's proxies all the way down (tuhhhhhrtle).
* Test early AND often.
* Automate
* Node.js is here to stay, because... JavaScript.
