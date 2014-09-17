# Monday 10:15-11:30 Advanced Web Forms
### Damian Edwards, Senior Program MAnager, ASP.NET

### Unit testing web forms
- Show of hands... only one guy in the room has done it!
- Separation of components is difficult
- Control handlers, et al are generally not testable
- It is possible to add MVC abstractions to your pages to do unit testing
- Just like MVC, still not going to test views/view event handlers
#### Example
- Can use a base class (TestablePage) that puts HttpContextBase, RequestBase, etc as testable properties on the page and then inject these properties into the page constructor. 
- The base class news everything up, and if it's not under test the null parameters can simply get their values off the HttpContext. 

- ASP.NET Web Forms MVP Nuget package provides testability.

### Friendly URLs
- Solution is available on damian edwards' github repo
- Map page route available in .NET 4.0
- Automatically generates mobile master page using browser caps
- Besides mobile, can also use for globalization.

### Request Validation
> "Request validation is one of the things we don't want you to use anymore...it actually makes you worse off and lulls you into a false sense of security." - Damian Edwards

- Sanitize your inputs and validate against expectations, etc
- Always encode user content that is output to the page

> "There is no way purely in configuration to turn request validation off."

- There is a Nuget package called DisableRequestValidation that will turn it off.
- This causes the request validation (which you can't turn off) to use a custom request validator that says that everything is okay.
- Properly encode output so that it won't render as html:

`<%: %>`

not

`<%= %>`

or in .NET 4.5:

`<%#: %>`

not 

`<%# %>`

- @ syntax in Razor (.NET 3) automatically encodes.

### Model binding in .NET 4.5
1. Create an instance of the model being validated
2. Create a FormValueProvider(), then

`TryUpdateModel(widget, valueProvider);`

- Validation on form elements is free without using data controls.
- Extension of value provider (AggregateValueProvider) can do validations against a combination of the form, the query string, cookies.
- Can do data binding dynamically from query string. Saves you from having to validate, handle nulls, try and parse different types into strings, by hand, and returns appropriate validation errors if necessary.
- Can also do this using dynamic types by passing an anonymous object into e.g. 

` ModelBindingExecutionContext.BindFromQueryString(new { Name ="", Description = "", Price = 0m});`

> "The primary purpose of the model binding system in .NET 4.5 is to prevent you from having to write code to pull data out of the request...[data validation] is free."

### Dynamic Data
- .NET 4.0 allows use of these features without having to create a special project type.
- Available as DynamicDataTemplatesCS in Nuget.
- Can extend handling on any control type and `<asp:DynamicControl />` will detect and use it.
- Even cooler: `<asp:DynamicEntity />`can generate a form that can edit a model provided.
- Templates are all available and editable in the project. 

> "If you have a ton of web forms and you're not doing this, I feel sorry for you!"

### Control Builder Interceptor
- Lets you change the code that is generated when a control is rendered.
- github.com/grabyourpitchforks/viewstate-compression
- Enables you to make large-scale changes across your entire application in one place.

### Asynchronous UIs and APIs
- `<asp:MultiView />` to only render part of a page (e.g. into an iframe)
- It's about preventing blocking, not about making stuff faster per se
- Never do async void (how does the caller know it's done waiting?)
- How to handle in PageLoad? `RegisterAsyncTask(new PageAsyncTask(LoadData));` 
- HttpTaskAsyncHandler for e.g. reading data from a fileserver; lets you split up files rather than typing up resources for the whole file.
- set `useasync="true"` on a filestream object and turn off buffering

@damianedwards
demos at github.com/damianedwards/anglebracketsspring2013






