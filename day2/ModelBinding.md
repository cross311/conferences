# Model Binding in MVC and Web API
#### Scott Allen - Monday 2:15-3:15

### Simple Binding
- ValueProvider gives you values from the HTTP request and is used by the model binder.
 e.g. 
`ValueProvider.ContainsPrefix("FirstName") // misleading method name
ValueProvider.GetValue("firstName")` 
gets passed to 
`[HttpPost]
 public ActionResult Create(string firstName) {}`
- ModelState gets populated when the model is bound; also houses IsValid() method
- Binding Environment populates the model with values from the various ValueProviders in a specified order: 
 - ChildActionVP 
 - FormVP 
 - RouteDataVP 
 - QueryStringVP 
 - HttpFileCollectionVP -- it will use the first provider that sees data.
 
### Security issue: over-posting/false assignment
- **Beware** of over-posting/false assignment: The model binder will accept and bind parameters it sees even if not exposed on the form
 - e.g. passing FirstName='blah' from a form that only has a last name field.
 - Can resolve by passing an interface to the model binder which only exposes the desired properties.
 - Can also use `[Bind(Include="Name, Hire Date"), Employee employee]`
 - Can also use MVVM

### Model Binders
- Default one does most of the work, but calls out recursively to see if any other binders have special handling for a type passed in.
- Default model binder only works with objects that have a default constructor (one that doesn't take parameters); try it and you'll get a no parameterless constructor error.
 - Need to create a custom model binder. Can inherit from the default and implement BindModel().
 - Model binder should put input parameters on the model state, so that validation can be handled without exceptions and values are retained to give feedback to the user.
 - Can also pass back custom validation messages.
 
### Web API Model Binding
- Primitive types have to be in the URL
- Complex types from the message body 
- Web API help Nuget package will show you what JSON needs to be posted to the model for proper binding.
- In general, to avoid trouble use a viewmodel or post using JSON.
 

Source code is at github.com/OdeToCode/MVC5_samples












