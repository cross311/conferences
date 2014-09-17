Sails.js
=============


* Two years ago Sails.js was born
* Complete server-side javascript backend web framework
* Built on Express
* Structured as a MVC framework similar to Ruby on Rails
* Two different types of incoming requests: HTTP, WebSockets
  * Eliminates the distinction between the two types of requests
  * Same interface for handling http, WebSocket requests
* Comes with an asset pipeline. By default Grunt is used but Gulp can be used
* Sails code follows Node.js best practices.
* Supports existing Express code
* Ships with an ORM. Follows the adapter pattern so one DB interface for various different DB backends. waterline.
* Put your data in the container that makes the most sense for it. Then join it together
* 