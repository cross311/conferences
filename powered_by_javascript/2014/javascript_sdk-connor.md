Javacript SDKs
============

Presenter: [braintree](http://braintree.com)
Writer: [Connor Ross](http://twitter.com/cross311)

## The Beginning

Braintree wanted to eliminate the redirect.  They encrypted all card data in the browser.  Credit card data never is sent to you browser, only encrypted data.

### The SDK

Switched from a client side encryption, to a token that is gotten after a credit card is sent to braintree for them to store it.  Do your own custom ui, drop in form, pay with paypal, raw javascript api.

They realized there were a lot of shared components.  And since they are a 3rd party library they had to be very concious of what they were forcing the developer to push to the client.

Started by using Bower.  They were pulling js files from other repositories.  Anything that was in a number of places are just put into a seperate repository where everyone pulls from.

Seemed as though a number of things started to be a lot of boilerplate code.

They started to notice that they had to start making private things public so that other modules could access then, but these are all private parts of braintree api, that the client should not need to access.  Doing module definition at the start of every file added 30 lines to every file, and if it ever changed.....

Managing this dependancy tree of all the different parts and their dependencies turned into a mess. They coudl only see it getting worse as time goes by.  SO the Switched.

#### CommonJs -> Browserfy

- Eliminate boilerplate
- Easily source modules
- share code between server and browser

browserfy standalone to export the written js files into a single file that can be shared.

#### Already In Production??

They had a lot of code that needed to be changed to the new model.  Some of the transforms could take 1-2 hours or 1 day.  Decided to do it by an internal presenation.
After the presentation doing a live coding where they transformed a module infront of everyone.

Changing over to commonJs and browserfy they were able to keep the exact same outer api. 

## The End

One way to write javascript. one way to build.  Ability to open source pieces but load the same way.