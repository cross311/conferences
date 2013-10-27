#

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
#### don't
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

