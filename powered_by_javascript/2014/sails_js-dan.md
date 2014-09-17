Sails.js!
============
Presenter: ??
Writer: Dan Hoizner

# Problem
* We're doing I/O completely wrong.
* Enumerating doesn't take that long, but reading/writing disk/network takes forever.
* Not acceptable!
* Concurrency should be easy.
* Threads should be used by experts only.
* Web servers are important, but you actually want to use a web framework.
* You don't want to be writing all the system calls...use an ORM abstraction... or something.
* Sails.js was born.

# Sails.js
* sails started off as a way of doing complete server-side Node.js
* sails is a backend web framework (runs on the server).
* built on Express
* uses socket.io for optional WebSocket support
* Your frontend is *not* completely restful.

# What does "backend web framework" mean?
* Handles incoming requests
* provides structure
* talks to your database(s)
  - MySQL/Redis/Mongo + associations
* NOT a frontend web framework (does not replace iOS/android/angular/ember/phonegap/backbone/less-sass

# Handling Requests
* Two different kinds of incoming requests:
  - http://
  - websockets
* sails eliminates the distinction between the two
* same server-side code

# Structuring your app
* MVC framework
* follows django/rails/grails/laravel/asp.net mvc/spring/etc
  - difference? sails is on node
* More conventions
  - asset pipeline
    - defaults to grunt
    - but gulp is ok, too.
* sails apps maintain Node.js best-practices
  - req/res
  - callback pattern
  - npm
* sails apps support existing Express code

# Databases
* Sails ships with an ORM
  - waterline
    - MySQL
    - PostgreSQL
    - MongoDB
    - Redis
  - Allows you to write custom adapters (LDAP, AD)
    - Oracle
    - DB2
    - SQL Server
    - 20 others
  - Allows you to put your data in the container that makes the most sense for it
    - Products - mysql
    - Users - postgres
    - Orders - mongo
    - Activity - redis
    - Administrators - Oracle
    - ExternalUsers - DB2
  - Join/associate across databases

# Resources
* [Sailscasts](http://irlnathan.github.io/sailscasts/)
* [Modern Web](http://modernweb.com/category/node-js/)
