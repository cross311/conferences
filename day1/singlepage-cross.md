# 0 to 60 with Single Page Apps & HTML5

Presentors: 

* John Papa (@john_papa)
* Ward Bell (@wardbell)

## Vanilla JS

A javascript framework that is one every single device that exists today!  If you just went *what*, let me explain what vanilla js is.  Vanilla js is the javascript language itself, or js out of the box.  Make sure that what you are doing actually needs a framework, because you can do a lot with out of the box javascript.

## SPAs

Definition: single page application.  Presentor is going to use angularjs as the spa framework for today.  Don't mix frameworks, pick one and stick with it.  Mixing spa frameworks is just asking for a jumbled mess!

Questions that you should ask when choosing a framework:

* What do I need?
* What options do I have?
* What do I need to know?
* What can I build?

If you can't get approval to turn your entire app into spa, just know that you can just do a small section as a spa.  Just phase in the spa, slowly taking in more and more pages that the spa handles.

## What do we want in a SPA framework

When the presentor codes he likes to write things that are single responsibility, so he also wants his framework to be written in this way also!

Apps should be written in small files, while each file handles one thing.  Each one names with what it handles.

Your SPA framework should make writing applications in this way easy.  The framework should contain **Routing** and **DI**.

With DI the framework will handle loading the files and the dependances that you will need to use in each class.

Routing is an absolute must have.  While the name of the presentation is Single page, you will be writing many views that are shown from this one page.  Routing handles moving from view to view, back and forth.

Data binding, how to keep the view up to date with models that are changing over time.  Do you have to refresh the whole screen. Do you have to manage how you display each model and keeping it up to date. NO, your framework should handle that.

Along with data binding, the framework should handle all the DOM monipulation.  DOM monipulation is the most expensive thing that you will do in the browser.  Let the framework handle this, so that you dont have to worry about destroying the browser.

How does the framework manage DOM manipulation?  DOM Templates should come standard with your framework.  You should only have to define how to display a model once and have that template be used everywhere.  Coming alon with this is **Views**.  You should not have to re-write the same bit of views over and over accross your application if they are all the same.  The framework should allow you to re-use views easily across the site.

* DI
* Routing
* MV*
* Data Binding
* DOM Templates
* Views

If you think there are some things missing in this list, you would be correct.  A SPA framework is a presentation framework.  It does not need to handle every thing, that is the idea behind single responsibility. You will need to load data from your server, handle security, and other things that are not related to the presnetation.

## Value of Presentation frameworks

* Reduces the Plumbing
 * There are a lot of things that have already been solved.  Let people who specalize in these things write the specialty code
* Handles the 
* TODO

## Conventional asp.net app

broswer client, html + jquery
Server: presentation, business logic, data access
Database

---

smart client
Desktop client, presentation ui logic, data access
server service
database

---

single page applications
browser: presentation html/css, ui logic, data service access
service: service content service
database

---

People who switched over to smart clients, have been using these concepts for quite a while.  How you do this on the client is pretty much the same, just without plugins and just using the browser.  Same architecture ... different technology

## SPA Features (Presentation FrameWorks)

* Orgnization
* Page LifeCycle
* Dependency Mgt
* MV*
* Routing
* UI Interaction
* Data Binding
* Services

What is ** NOT **

* Rich Data
* UI Controls
* Testing
* CSS / Styling
* Your Logic :)
* Security

Picking which SPA framework based off of the Todo app example. hahahah.  It is not for deciding, but ot see how the framework style looks. Ask **WHY** 5 times before you make any decisions.

A presenstion framework should do presentation well.  jQuery and other frameworks in js are just doing way to much so that puts them in a position where they give you the kitchen sink, but that isnk is not the best.

## Data Binding

With angularjs, your databinding is just {{variable}} with in the html. there is no <%= variable %>.  You should not have to write so much.

When working with attributes that are on html elements, always start with data-.  You techinically do not have too, but in html5 it is a reserved attribute name that does not slow down the browser from trying to see if it understands what you are saying.

## MV*

How to you attached you html to you model to your view. No javascript in the view, an dnot html in the viewModel.  With Angular you should not have to mix these two items.  Putting this information in each, it makes reading and understanding in the long term very hard.  What should the screen present is the view.  The actual data that the needs to be updated or seen is the ViewModel.

Putting you View without having js mixed it, it allows you to make sure that you html is valid.  Putting a view together by appending strings on strings, how do you know that you are writting valid html?  Browsers and other things have been built to do things really well, when you mix js and html you are saying that you dont care that they do it better.

## Dynamic View Composition

View do not have to have everything in them.  Your views should also handle one thing and one thing only.  use views inside of views inside of views.  Then you only have to worry about exactly what you are trying to view in one html file, not everything in one html file.

