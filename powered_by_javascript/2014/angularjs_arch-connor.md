AngularJS Application Architecture That Won't Make You Cry
==========

Presenter:

Writer: [Connor Ross](http://twitter.com/otter311)

Presenter is using web storm.  Most of the talk will be how to organize your code.

Have a folder that the server will read from, and things are organized in a way that the server understands most.  He calls it build.

The folder that he actually develops in is src folder.  Highly recommends usng gulp or grunt, but some kind of task runner.

Wrote his own injector to place css and js files into the index html so that you dont have to manage placing script/stylesheet nodes for items the build process knows about.

For each page (he calls it module) he creates a new module with the name of the module namespaced. ex 'website.about' where about is the module name.  Each module is in its own folder structure, given the example there would be an about folder.  Have enough seperation to make it easy to comprehend, but dont split it up so much that you cannot find anything.

```

- app
|
| - app.js 
|
| - about
| | - about.js
| | _ about.tpl.html
|
| - experiments
| | - experiments.js
| | - experiments.tpl.html

- common
| 
| - common.js
|
| - models
| | - state-service.js


```

Using a tool to take `<htmlFilename>.tpl.html` and places them into a js file that puts all the html files into the angularjs template cache. `html2js` is the name of the plugin.

If things are used accross modules puts the thing in a common folder.

Dont do && expressions in ng-ifs, always put it into a method.  Fat Models skinny Controller, stolen from rails.

Recommends `lodash`  also recommends `functional javascript`

egghead.io

http://j.mp/sl-egghead

https://github.com/simpulton/angular-website-routes (refactor branch)

