Is SPA right for every app? No, not for everything. You can't solve the problem of everything in any one technology. 

The right questions:

* What do I need?
* What options do I have?
* What do I need to know?
* What can I build?

What is a SPA?

* Single Page Application written in HTML/CSS/JavaScript
* Executing on the client
* SPA is a terrible name
	* "I can only support one page."
* Examples:
	* Trello
	* Gmail
		* Silos of SPAs
			* Inbox
			* Calendar
			* Contacts
	* Code Camper

What are you trying to solve?
* Reach
	* Ubiquitous
* Rich
* Reduced round tripping
	* Reduce the amount of constant cross-network chatter
	* Certain apps can run offline
		* Cache all the key information

Common Traits:

* Navigation, History, Deep Linking
* Persisting State
	* Localstorage, Cloud backup
* Mostly Loaded on Initial Page

Confused on how to build a SPA?
The cool kids use a presentation framework. (Not the reason to use it). Use a SPA if it makes sense for your application. Sometimes the right answer is build multiple native apps, sometimes the answer is use something like PhoneGap, sometimes build a SPA.

Value of Presentation Frameworks:

* Reduces the plumbing
* Handles the monotony

Where Will You Spend Your Time?

* Without a presentation framework, you will spend half of your time building out features that a presentation framework will give you.
* Testing
* Security
* Stories (*where you want to be*)

In other sense, compare to languages where you need to implement your own garbage collection.

How Do I Do That?

* Get the information needed to display on the screen.
	* Partial models.
* When you drill into a model, load the full model to display the rest of the information.
* Localstorage lets you persist form data across browser restarts
* Storage
	* Breeze.js
	* IE8+ support
		* storage.js
		* amplified.storage (maybe IE6/IE7)
* Frameworks
	* Angular.js
	* Durandal
	* Backbone.js
	* Ember.js
	* Batman
	* React

What does it do?

* load a shell and initial content
* display changing data
* navigate screens w/ deep linking
* load screens dynamically
* data on demand
* share data across screens
* accept user input ... validate ... save
* store data locally
* "Responsive Design"

What doesn't it do?

* Rich Data
	* Better to do one thing well and hook into others for support/expansion
* UI Controls
	* Lets you use your preferred control
* Testing
* CSS / Styling
* Your logic
* Security

More than Just Get and Post

* Breeze.js
	* Client caching and sharing
	* Queries (remote and local)
		* OData
	* Extend the model on the client
	* Object graphs
		* Manage objects so there is no duplicate data
	* Local storage
	* Async / Promises
	* Share data across views

How do you choose?

* Are the differences stark?
* Find the seven differences
	* Not so different after all
* Two ways:
	* "Cool Side of the Pillow" perspective
		* [fill-in-the-blank] feels more comfortable
		* Angular is by Google, so it will be around forever
			* Um, yeah. You go with that.
		* Both are complete frameworks
			* Neither has everything
			* Both have intentional gaps
			* Angular has moved to more modular Legos like Durandal
		* Angular has everything I need in 1 place, while Durandal uses require.js and knockout.js
		* Angular uses POJO, Knockout has functions
			* Durandal offers POJO with its observable module

Implementation differences:

* Promises
	* Durandal uses jQuery promises (though you can use q with it)
	* Angular uses `$q`
* DOM Interaction and Wrapping
	* Angular uses directives
* Routing
	* Angular has $route, Durandal has router module
* Both are MV* and arguably both MVVM
* Dependency management
	* Durandal depends on require.js
	* Angular has built-in DI (can use require.js)
		* Makes testing really easy
* Community
	* Angular has rich community support
	* Durandal is growing

Change detection differences

* Angular
	* Dirty checking
	* Angular watches your models via digest
* Knockout
	* Observer pattern
	* Knockout observes your models

What do I need:

* Score card
	* Presentation
		* MV* - both
		* Routing - both
		* Data Binding - both
		* View composition - both
		* Animations - both
	* Code management
		* Pub/Sub messaging - both
		* Dependency management - both
		* Testable - both
			* Testability features - Angular+
				* Integrate well with Jasmine
	* Data management
		* Promises - both
		* Breeze!
			* Querying
			* Caching
			* Validation
			* Self assembling object graphs
			* Saving change-sets

Update the screen when data changes:

* Durandal/KO
	* binds to observables
		* Title property and button-states are observable
		* Deleting session.title value triggers:
			* session change state
			* validation message
		* KO observes these changes and updates screen
			* Like `INotifyPropertyChanged`
* Angular
	* Dirty checking
		* Unique to angular, actually works
	* Bind to any JS object ... w/o touching it
	* Performs well on modern browsers ...
	* ... up to ~2000 data bound values (a lot)
	* ... if you avoid slow binds
	* Must learn the $digest cycle eventually
	* Learn when to call (and not call) $apply
	* Pay attention to performance-killing slow function bindings
		* Filters on displaying data can SUCK on an object that changes a lot and is tied to lots of other objects
	* Beware of older browsers ( < IE9 )
	* These are non-issues in Durandal
		* No magic in Durandal
	* POJOs
		* Durandal's POJO plugin
			* Turns POJOs into observables automagically
	* Angular's dirty checking = +++
		* Easy and intuitive
		* less code
		* Best technical reason to prefer angular

One framework to rule them all?

Nope. Who knows what will be around in 10 years?

#Resources

http://jpapa.me/SPAJSPS durandal and breeze
http://jpapa.me/SPANGZ angular and breeze
http://johnpapa.net/SPA resources

Single page apps jumpstart
Build a Single Page Application (SPA), in JavaScript and HTML, with a rich user experience and runs on almost any device!