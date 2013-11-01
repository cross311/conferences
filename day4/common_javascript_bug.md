* Missing mark bug
	* Automatic Semicolon Insertion (ASI)
		* http://es5.github.io/#x7.9
	* Semicolon-less JavaScript Rules
		* Don't end your statements with a semicolon
		* If statement starts with `[`, `(`, or a binary operator `(+*/-,.) then insert a semicolon before it
	* Use Semicolons As Expected
		* Follow the official specification when semicolons are required
		* Use tools like JSLint or JSHint to give you feedback and integrate into your code editor
* Fresh function bug
	* Polyfill
		* es5-shim - https://github.com/kriskowal/es5-shim/
	* Shim
		* Underscore.js - http://underscorejs.org/
		* Lo-Dash - http://lodash.com
	* If you use a `filter` and a `map`, you can replace with `reduce`
* Tumble through bug
	* missing `break;` on `switch(){case: break;}`
	* JSHint warns, but supports `/* falls through */` to suppress 
	* Alternatives to switch:
		* key/value lookup dictionary
		* add function that exposes your expected result
* Strictly Stray Bug
	* when minimized, `"use strict"` persists across your entire bundle
	* **Use strict mode**
		* can apply to whole script
		* Better to apply **per function**
		* Wrap a function in parenthesis to force immediate execution
* Fickle Figure Bug
	* trailing comma
		* throws error in IE7
		* ECMAScript 5 doesn't care about trailing commas
		* IE8
			* trailing comma increases length of array by 1
		* JSON.parse() doesn't like trailing commas
* Mistaken Mold Bug
	* typeof array != "array"
	* jQuery - `$.type()`
	* Underscore Lo-Dash -> helper methods - `_.IsArray`
	* ECMAScript 5 - `Array.IsArray()`
* Twisted Truth Bug
	* 0 is not truthy
	* Truthy/falsey rules
	* Check `price !== undefined` rather than just `price`
* Crafty Convert Bug
	* `""` coerces to `0`
	* `"1"` coerces to `1`
* Confounding Context Bug
	* Be wary of `this`
* Booked Byword Bug
	* reserved keywords
	* In ECMAScript 3, reserved words cannot be used as identifier names or identifiers
	* In ECMAScript 5, reserved words cannot be used as identifier names
* Relative Realism Bug
	* USE IIFE to protect undefined and help with minification
* Tangled Tag Bug
	* browser automatically puts IDs/classes on the global namespace
	* IE8 doesn't let you override what it did
	* introduce an additional scope to fix

Elijah Manor
http://elijahmanor.com
@elijahmanor