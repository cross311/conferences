* Immediately Invoked Execution (IIE) function
	* Don't pollute the global namespace
* grunt
* QUnit
* Jasmine
* github.com/wardbell/jsTesting.git

##Testing

Modules:

    module("First Tests");
    
    test("always passes", function () {
        ok(true, "it passed");
    });
    
    test("always fails", function () {
        ok(false, "it failed deliberately");
    });
    
    test("expects exactly 1 assert", 1, function () {});
    
The point of counting assertions is to make sure you hit all the paths that you expect to during your test. This way, if you comment out an assertion, or have the code bail before the assertion is hit, the test will fail.

* The `equal` assertion gives you expected and actual in the output.
* `deepEqual` does `===`
	* No type coercion
* `deepEqual` checks value equality, not reference equality

Error checking:

    raises(function () {
        throw new CustomError();
    }, CustomError, "must throw CustomError");

"dirtying the resource"???

    module("Module tests",
        setup: setup,
        teardown: teardown
        
Write your own function (if necessary) to build a custom assertion.

Long running functions:
* Test can run through, executed setTimeout, didn't execute callback
	* Test passes
	* "global failure", not associated with a test.
* Fix: `asyncTest`
	* Must remember to call `start();` to resume testrunner
* `QUnit.config.testTimeout = 3000;` (no test can take longer than 3 seconds)