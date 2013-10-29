Designing RESTful Services with asp.net Web API
===

Presentor: Brian Noyes (@briannoyes)

## Web Api

Came out with 4.5, platform for building http web services.

You can mix Web API projects in with old school asp.net projects.  Idea of web api is to make wcf simplier.  Apparently the web api team was a offshot from the wcf team.  Build service taht is consumption from multi-platform.  In 4.5 no wcf stuff anywhere in the stack of web api.

Built a wee bit on top of the MVC structure, service are controllers.  Embrace http compared to wcf that wants you as far as possible.

The stuff we are talking about today is buildign services that other people ar going to be useing. if you are just building a service that you are using it does not really matter what you use, you control both sides they just need to talk to eachother.

Uses many parts of MVC as i mentioned earlier.  Another part they use is routing, model binding, and action filters (authorization).

Big concept is Convention over configuration!  Content negotions are contained to do many languages of languages you can export as custom formatters.  json, Xml, odata (nuget).

Gotcha that you need to watch out for is the fact that if a method signature does not exactly match the parameters that are passed in, it will fall back to the defautl method without any parameters.

## REpresentational State Transfer

Rest is a architectural style, SOAP is a protocol.

Full Embrace of HTTP spec.  

"ReST in practive" Jim Webber

[Rest APIs must be HuperText driven](http://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven)

### Architectural Contraints

Client server, stateless, cache, Layered architecture, Uniform Interface, Code On Demand

Get has to be a replayable request, any change in response should not be from your call.

*Note: Good bit of talking going on here, but a lot of it is true definition of REST*

Richards maturity model for REST.

Talks about using HAL standard to adding in URI hyperlinks.

Blog post on [BrianNoyes.net](http://BrianNoyes.net)