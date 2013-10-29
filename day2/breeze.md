#Breeze
##SPA Architecture
* New way of thinking of browser / HTML apps
* AJAX -> evolved
	* Smarter clients
	* More focus on the client side, less on the server
	* One page load
		* Sub-applications in the overall system/application
		* Do not need to refactor ALL your existing WebForms/MVC pages into one
		* Can be done in chunks
		* Multiple SPAs within the application
		* Islands of stateful, highly interactive, client-driven pages
		* Stuff happens in the page to change the content of portions of the page
		* Feels like a smart client / desktop app, but in the browser
			* Can also be packaged as an installed app (iOS, Android, WinRT, WP)
		* Smart Client <=> SPA
			* Only difference is the languages used

##Breeze Overview

Breeze targets UI logic and Data/Service access.

* Data service calls
	* CRUD centric
	* Web APIs or OData
* Retrieve and update data from the JS client
* Perform rich client queries
	* Client expressed, server executed
	* Farm out to LINQ, SQL Server set operations
	* Filter, sort, page, expand, select
		* Expand --> be greedy, eager loading
		* Select --> select the properties you care about
			* Don't waste bandwidth grabbing unnecessary properties
	* Cache retrieved entities
	* Track changes on cached entities to figure out what to send back to the server
	* Validate entities
	* Work well with data binding frameworks
		* Built in mappings to data-bindings, observables in Knockout, etc.
			* Knockout.js
			* Backbone.js
			* Angular.js
			* Ember.js
	* Save changes offline
		* Cache lookup lists and write into local browser storage
		* Persist form data across visits

###Two Sides of Breeze
* Client
	* JS client data retrieval, update, and manipulation
* Server
	* `BreezeController` / `EFContextProvider`
		* Code-first DBContext Entity Framework
	* Can I use breeze without OData, EF, NHibernate?
		* Yes, but is it worth the effort?
		* Good for Rave? Probably not (Damn).

##Retrieving and querying data

* Uses standard OData syntax in the queryString to build a .NET expression tree

##Updating data

* Data round-trips to the client on update/save
	* Allows you to retrive auto-generated IDs, concurrency fields, etc.
* Sends back original values to allow auditing, etc.
* Uses promises
	* `.Then(func1).Fail(func2)`
* Exposes `StringLength` and `Required` DataAnnotations currently
	* More to come?
	* Others don't automatically get generated, but Breeze does provide built-in validators
* Validation happens on:
	* `SavedChanges`
	* Attach entity to cache
	* Create entity (automatically attached)
	* Manual validation
		* `.entityAspect.validateEntity()`

##Working with OData

* Can use OData services instead of a `BreezeController`
* SharePoint, IBM, Sun all expose and consume OData
	* Microsoft dominated in terms of the spec
* Changes needed:
	* Configuration
		* `breeze.config.initializeAdapterInstances({ dataService: "OData" });`
	* One additional JS library
		* datajs (open-source MS library)
* Breeze always uses OData query syntax in URLs
* Making these changes will use full-blown OData syntax for all operations

#References
* Brian Noyes Breeze Pluralsight Course
* Brian Noyes OData/WebAPI Pluralsight Course
* SPA jumpstart papa
* SPA with angular and breeze papa
* [Breeze Conceptual](http://breezejs.com/documentation/introduction)
* [Breeze API](http://breezejs.com/sites/all/apidocs/index.html) (Updated *before* conceptual docs)
* [Breeze Unit Testing Sample](http://breezejs.com/samples/doccode)
* [Pain Free Data Access in JavaScript, Julie Lerman, MSDN Magazine](http://msdn.microsoft.com/en-us/magazine/jj863129.aspx)