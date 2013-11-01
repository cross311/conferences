Unit Testing 101
===

Presentor: Paul Litwin (@plitwin)

Target:  Developer, currently not unit testing, not sure how to employ it, don't know where to start.

## What??

Unit tests -> Automated tests for icolated unit of code.  by devs

Intergration tests -> tests that go accross units of code

System testing -> entire system, by testers


## Why??

ensure code performs as intened.  Units should be small typically a method.  if bigger then that then maybe you need to break something down.  Can servce as built in documentation.  Allow safer refactoring.  MAKES you code BETTER!  Normal good code is pretty easy to test.

Against??  You have to write more code in addition.  Some things are harder to test.  Requires planning.

## Starting

Start off with just a few tests.  You dont have to start off with testing the hardest thing in the application.  Start off with parts of the code that are goign to have the most impact for your work.  then just add more tests as you go.

*Note: Going through adding tests for very very basic MVC Controller methods.*

## Dealing with data access

Presentor generated a controller from a view using the visual studio scafolding.  It uses the entity framework db context to load the data in each method.  So from this he is going to try and create a test.  The test does not work, it blows up because we do not have the stuff needed for entitiy framework to work or do we have our db strings set up.... 

How do you handle this??  Start off by creating more lossly couple components, usign interfaces.  To tie concrete implementation use DI.

*Note: ran out of time*