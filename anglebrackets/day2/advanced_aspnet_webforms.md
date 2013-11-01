#Monday 10:15-11:30 ASP.NET Web Forms - Damian Edwards
##Unit Testing WebForms

###Modifying the Code-Behind to Promote Testability
* `Page_Load` calls out to separate logic method
* Base class `TestablePage`
	* Abstracts various HTTP objects (request, response, context, session, etc)
	* If objects are null, wrap up in mockable wrappers
	* `HttpRequestBase.QueryString["test"];`
	* Framework: [ASP.NET Web Forms MVP](http://webformsmvp.com) (available on Nuget)

###Friendly URLs
    var settings = new FriendlyUrlSettings()
    settings.AutoRedirectMode = RedirectMode.Permanent;
    
    routes.EnableFriendlyUrls(settings, new DeviceSpecificWebFormsFriendlyUrls());

* Friendly URLs can automatically choose to use `Site.Master` or `Site.Mobile.Master` based on `browsercaps`
* Use for regionality/localization

Custom FriendlyUrlResolver to route device-specific masters/pages:

    { "Opera Mobi", "OperaMobile" }
    { "iPhone", "iPhone" }
    { "iPad", "iPad" }

###Request Validation
* **DO NOT USE**
	* No way to fully turn off in configuration
	* Use ASP.NET Request Validation Disabler NuGet Package
* Do your own field validation
* Always encode output to page
	* `HttpUtility.HtmlEncode("");`
	* **NEVER** use `<%= %>`
		* use `<%: %>` or `<%#: %>`
	* `@` syntax in Razor automatically encodes
	* If you need to output raw HTML, use `HtmlString` class

###Model Binding
* Bind controls to objects (`new FormValueProvider)`
* `TryUpdateModel(Class, IValueProvider)`
* Check `ModelState.IsValid` to check result of `TryUpdateModel`
	* Respects Data Annotations (`StringLength`, `Required`, etc)
	* Does not require data controls, can be done with raw HTML objects
	* Errors are shown on the page using the `asp:ModelErrorMessage` control
* Use an `AggregateValueProvider` to mimic MVC behavior
	* Fetch data from Form, QueryString, Cookies, etc in specific order
	* This allows you to use data from the QueryString to replace data from form fields, combinations, etc.

Extension methods:

    public Widget Model;
    Model = ModelBindingExecutionContext.BindFromQueryString<Widget();
    
Dynamics:

    Model = ModelBindingExecutionContext.BindFromQueryString(
        new { Name = "", Description = "", Price = 0m });

Model binding engine in 4.5 lets you forget about extracting data from the various containers as well as validation using data annotations. GORGEOUS.

###Dynamic Data
* Field templates, Entity templates
* `_Edit.ascx`, `Insert.ascx`
* OLD:
	* `asp:DynamicControl`
	* dynamic control templates are fully editable by user and allow consistency across the product
* NEW:
	* `asp:DynamicEntity`
	* Renders form based on POCO and data annotations

###Control Builder Interceptor
* [Github](https://github.com/GrabYourPitchforks/viewstate-compression)
* Add phantom properties
	* Add your own properties to controls by only adding in one place
* Ideas:
	* Replace WebForms data-binding with WPF data-binding syntax

###Async
* Async UI
	* `asp:MultiView`
* Async API
	* `async`/`await` WIN
	* `Async="true"` on the page
	* `Async void` is **EVIL**
		* No returns from an event handler
			* `RegisterAsyncTask(new PageAsyncTask(method));`
			* These get kicked off after `PreRenderComplete`
	* HttpTaskAsyncHandler
		* `public override async Task ProcessRequestAsync(HttpContext context)`
		* `useAsync: true` on `new FileStream`


##NuGet Packages
* Glimpse
* ASP.NET Request Validation Disabler
* DynamicDataTemplatesCS
* Modernizr

#Resources
* [Damian Twitter](http://twitter.com/damianedwards)
* [Damian Github](http://github.com/damianedwards/anglebracketsspring2013)
* [Stack Overflow](http://stackoverflow.com/a/12628170)
