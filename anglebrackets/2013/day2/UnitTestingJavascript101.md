Unit Testing javascript 101
===

Presentor: Ward

QUnit:

```js
(function() {
"use strict";
	
	module("First Tests");
	
	test("always passes", function(){
		ok(true, "it passed");
	});
	
	test("always fails", function(){
		//make it fail
		ok(true, "it fails deliberatly")
	});
})();
```

Developer trick: in chrome open developer tool and do Disable Cache while developer tools is open.

QUnit allows you to tell the test framework the exact number of ```ok's``` it should find.  This allows you to know that you are actually testing what you are trying to test.  Protects you from if a assertion is skipped for some reason.

Gotcha is the type coercion, just like in normal javascript dont do double equals.  If you want to do a real equals and make it explicit, use deepEqual method.  The nice part about equals tells you the two values so that you can actually see what it messed up on.  the normal equal only does double equal.

If you are trying to compare complex objects a normal equal will not check if the attributes are the same, if you want this use deepEqual.

You can also do exception tests by using the raises method.  You can also check and see if a custom error if you pass in a class as teh second param.

One thing about running these tests in the browser, is that the domain is going to be dirtied from test to test.  to get around this in the module definition you can define a setup and a teardown method.  the teardown method should un dirty anything that the module messes with.

## Custom Assertions

If you are testing floating point numbers, then you can write a isBetween method.  this allows you to test your output numbers that are within the spec.  This is an exapmle where you will need to write your own assertion.  This is recommended by the presentor.  This will also help readability of your tests.

## Async

A lot fo the code that you are going to be writing is code that will not be able to be tested sync.  How do you test Async code??  To be able to test async code you will need to use asynctest, and also will need to call a start() method when the async call returns.  If you leave out the start method it will timeout the test runner.

Async is the big thing to take away from this talk.  One thing to note: even if your using a promise system and you make it return right away by mocking the async call.  The promise system will make sure it ticks the clock at least once so that it will not run in teh single line.

*Note: Grunt - javascript nodejs task runner*

Grunt is a great tool for keeping track of your javascript in realtime coding.  You can set grunt to watch whenever you make a file change.  This will allow you to lint you code as you code.  Which without a good ide, this is a great companion.

