Herding JavaScript Cats with Dependency Management
Ward Bell
WardB@ideablade.com
@wardbell

Rich Data is a Breeze

Target: Single Page Apps

* Execution on the client (in the browser)
* Many application components (separation of concerns)
* Lots of files (until bundled and minified)

Modules Galore!

Challenges:

* Know which scripts to load
* Load the scripts in the right order
* Acquire components with dependencies

DI creates and delivers objects that depend on other objects.

What is a dependency?

* object *{title, getData, onChange}*
* function *function doTheVoodoo(){...}*
* primitive *"http://www.breezejs.com"*
* null ... with a side effect *e.g., a plugin*

What else can it do? Loading modules is a separate concern, but the DI system might do that too.

YAGNI?

Frameworks with DI built-in

* Node
* Durandal
* Angular

Acquire objects with dependencies:

* create, typically with the `new	` operator
* find in a global variable
* pass into the component

* Create with `new`
* Create with `new` and globals

DI with define

    define('D', function () {
        return { /* stuff */};
    });
    
    define('B', ['D'], function (d) {
        return { d: d, /* other stuff */};
    });
    
    define('Thing', ['B', 'C'],
        function (b, c) {
            return function (a) {
                this.b = b;
                this.c = c;
                // do stuff
            };
        });
        
        define('C', ['D', 'E'], function (d, e) {
            return {d: d, e: e, /* other stuff */};
        });
        
        var Thing = require('Thing'); //Creates *Thing* and *B*, *C*, *D*, and *E*
        var thing = new Thing(a);
        
        var Thing = require('Thing'); //uses already created *Thing* and dependencies
        var thing2 = new Thing(a2);
        
Require.js - **A JavaScript Module Loader**

AMD - Async Module Definition

* know the module file dependency chain
* Load files asynchronously on demand
* Keep track of what has been loaded

RequireJS registration syntax

    /* ~/app/services/datacontext.js */
    define([
      'durandal/system',
      'services/model'],
      **datacontext**);
      
    function **datacontext** (system, model) {
      ...
    }
    
RequireJS loads the *datacontext.js* asynchronously
Module name is filename segment, **'services/model'**
Definitions are purely positional, this lets you map `jquery` to `$`

Best-practices with RequireJS (because it's a PITA): 3rd party libraries in index.html, application stuff follows/uses DI.

Durandal 2.x assumes no global libraries, expects jQuery and knockout to be defined through RequireJS:

    define('jquery', );
    define('knockout', );
    
AngularJS:

* DI **is core to AngularJS**
* DI in AngularJS allows you to declaratively describe how your application is wired.
* Any component ... can easily be replaced.

Syntax:

    angular.module('app').factory('datacontext',
      ['common',
       'config',
       'entityManagerFactory', ...
      datacontext]);
      
    function datacontext(common, config, emFactory, ...) {
      ...
    }
    
* Angular can't load script files itself.
* Module name is explicit, 'datacontext'
* Angular module registration methods
* Closing bracket after the function reference
* Singleton
	* .factory
	* .service
	* .value
	* .constant
* Per-instance
	* .controller
	* 