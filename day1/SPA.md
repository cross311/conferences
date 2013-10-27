#First session

##Single page applications

Focus on ways to turn parts of existing legacy apps into SPAs: Great way of modularizing monolithic apps (can roll out piecemeal)

###What do we want in a SPA? 
- DI: manage separation of concerns, 
- Routing (+ deep linking), 
- MV* have clean models, 
- data binding, make it easier to add new AJAX functionality etc
- DOM: Most expensive thing to do in a page: changing the DOM (reflow)
Also: views, security, SEO, *data*

#####SPAs - get necessary code into page

### Presentation frameworks
#### do
- Reduce plumbing
- Let you focus on translating domain specific knowledge into code
- Lets you focus on user stories
#### don't do
- Rich data, UI controls, testing, styling/CSS, logic, security

##### SPA features: Organization, Page LifeCycle
On choosing a framework:
> "They're gonna pick what to do on a 70-page app based on what they learned building a to-do list app" - John Papa

### Angular overview
- HTML5 convention: all new attributes should start with data- (reserved). So for angular, use data-ng-click et al.
- jQuery is unnecessary and probably takes more code
- handles databinding, not just on functions, but on selectors
- supports MV* --
##### MVVM -- no JavaScript in the view, no HTML in the ViewModel


#Second session-----------------------------------------
### Getting Angular
- Nuget -- AngularJS.Core is the minimum install

### Basic usage
- Attributes vs. mustache syntax: attributes will bind as soon as the HTML loads, as opposed to when the JS loads at the bottom of the page.

###Recommended conventions:

- One convention: put everything you can bind to at the top of your controller.
- alias 'this' as something semantically meaningful, e.g. vm for viewmodel
- 'controller as' syntax is new in angular 1.1.2, enables you to do vm.property in the view.

Directive
  //\\
//    \\
JS====HTML

- Check out existing angular directives before trying to implement anything
- Side waffle: open source templates for VS, by VS team to aid in organization that include angular controller, directive, and module templates. 

### Dependencies
- Specify your dependencies and inject
- Dependencies must be specified in the same order when registering the controller as in the function signature

### Setup
- When your angular app starts -- Angular registers your module (name/dependencies) e.g. app.module()
- App is configured e.g. (app.config(['$routeProvider', routeConfigurator]));
- Side note: dynamically adding routes doesn't work well in angular
- Next app.run() is hit and e.g. calls services that setup data, etc

### Routing
- Each route has a different config; can use this to set up deep linking and specifying templates to handle parameters
- Angular uses hashtag routing to handle many routes without leaving the client side

### View Composition
- Templates placed in ng-view
