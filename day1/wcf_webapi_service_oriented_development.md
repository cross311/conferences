#SOA:
* SOA is not just for enterprise-size applications
* "The decomposition of a system into autonomous or nearly autonomous units of responsibility and exposure."
* Exposing an API protects service developers from stupid client developers.
* Example: Zip Code API
     - Prevent updates, prevent access to confidential information.
* All dependencies are abstracted by the service layer from the client layer

#In The Old Days:
* .NET Remoting
     - .NET to .NET only
     - cryptic configuration
* Web Services
     - HTTP only
     - bad practices
     - required WS* for any advanced capabilities
* Enterprise Services
     - PITA to setup and work with
* MSMQ
     - has its own API

#WCF and WebAPI:

##WCF vs WebAPI:
* WebAPI has killed WCF --> *"The report of my death was an exaggeration."* - Mark Twain
* WCF and WebAPI both have their own uses.
* WebAPI has a much smaller scope and learning curve than WCF.
* One is NOT a replacement for the other
* One is NOT better than the other
* WCF is WAY more feature rich
* Web API is WAY more interoperable
     - no tooling necessary
* WCF is based on SOAP protocol
* Web API is based on REST architecture
* WCF DataContracts mirror WebAPI Models

##WCF with WebAPI:
* Write services in WCF and extend with WebAPI


#WCF:
* What does WCF have that WebAPI doe not?
     - Instancing & Concurrency
     - Operations
* The artist formerly known as Indigo
* Provides a declarative and pseudo-aspect-oriented model for managing features
     - transactions
     - security
     - reliability
     - state
     - etc.
* Interception Model Architecture aka pipeline architecture

##WCF Parts Breakdown:
* System.ServiceModel
	  - Assembly & Namespace
* Data Contracts
     - Needs to be known by client AND service
* Service Contracts
     - Needs to be known by client AND service
* Services
* Service Hosts
* Client Proxies
* Client
* Configuration

##Sample Project:
Solution layout

* **Essentials.BusinessEngine**
* **Essentials.Client**
* **Essentials.Contracts**
     * Add `System.Runtime.Serialization`
     * Add `System.ServiceModel`
* **Essentials.Host**
* **Essentials.Services**
     * Services separated from Hosts to allow transport over different avenues (i.e., Not just HTTP).
* **Essentials.Proxies**
     - Parallel to Essentials.Services on the client-side
	      * Has reference to **Essentials.Contracts**
		  * Proxies extend `ClientBase<T>` where `T` is your service contract
		  * Proxies also implement service contract
* **Essentials.WebHost**

`DataContract/ServiceContract/OperationContract` serializer is more forgiving
     
* won't break if the service adds more properties that the client doesn't know about
* ExternsionDataObject (IExtensibleDataObject)
     - WCF throws extra properties that service doesn't know about into the ExtensionDataObject
	   in order to minimize/build-up contracts
* Everything with the DataContract, ServiceContract, OperationContract decorators is opt-in
*  `[DataContract]` on class --> `[DataMember]` on properties
* `[ServiceContract]` on class --> `[OperationContract]` on methods
* Shared `[ServiceContract]` is an interface, not a class

One `ServiceHost` per service:

    var host = new ServiceHost(typeof(GeoService));
    host.Open();
 
Service configuration:

    <system.serviceModel>
      <services>
      <service name="Essentials.Services.GeoService">
        <endpoint address="net.tcp://localhost:8009/GeoService"
                            binding="netTcpBinding"
					        contract="Essentials.Contracts.IGeoService" />
		</service>
	  </services>
	</system.serviceModel>
	
WCF is the only technology out of Microsoft with meaningful error messages.

    The contract name "" could not be found in the listing of contracts for service "".
	
Proxies abstract calling the service via `ClientBase<T>`, i.e.:
	
	public ZipCodeData GetZipCodeInfo(string zip)
	{
		return Channel.GetZipCodeInfo(zip);
	}
	
This allows you to ignore and not have to implement *insanity-level code*:

    var client = new GeoClient();
    var data = client.GetZipCodeInfo(text);
    if (data != null)
    {
      // call successful
    }
    client.Close();
	
Client-side configuration:

    <system.serviceModel>
	  <client>
	    <endpoint address="net.tcp://localhost:8009/GeoService"
                  binding="netTcpBinding"
		  	      contract="Essentials.Contracts.IGeoService"
				  name="tcp" />
	  </client>
	</system.serviceModel>
	
This configuration is what ties together the `ClientBase<T>` plumbing.
The name attribute allows redundancy on service endpoints, i.e. try TCP first and HTTP on failure.

WCF 4.0 and up allows virtualized .svc files (no more physical .svc/.asmx files) by using
serviceHostingEnvironment:

    <serviceHostingEnvironment>
	  <serviceActivations>
	    <add service="Essentials.Services.GeoService" relativeAddress="GeoService.svc" />
      </serviceActivations>
	</serviceHostingEnvironment>
	
##Instancing and Concurrency

Service instantiation can be *per-call*, *per-session (default)*, *singleton*.
`InstanceContextMode` and `ConcurrencyMode` control behavior.
In *per-session* mode, the lifetime of the service instance is tied to the lifetime of the proxy.
In *singleton* mode, everything sucks, as usual.
*Per-call* is inherently thread-safe, but not concurrent by default. `ConcurrencyMode.Multiple` is necessary for that.

**Best-Practice:** `InstanceContextMode.PerCall` and `ConcurrencyMode.Multiple`.

###Operations:
* Request/Response
* One way call
* Callback

####Request/Response 

This is the default for all operations, even void returns. This blocks the client thread until the request is complete regardless of service concurrency mode.

####One way call 

One-way calls forgo the response. This frees up the client thread immediately after the request is made, but means that the client cannot know that anything went wrong in the service while processing the call.
     - `[OperationContract(IsOneWay=true)]` **must be a void return**

####Callbacks

    public interface IMyCallback
    {
    	[OperationContract]
	    bool ReportProgress();
	
    	[OperationContract(IsOneWay=true)]
	    void PerformCallback();
    }

Callbacks can pair up with one-way calls, or can provide responses on all methods. This allows the client to free up the main thread while the service executes a long-running process, but still lets the

Callbacks are defined by `[ServiceContract(CallbackContract=typeof(IMyCallback))]` and require the proxy to inherit from `DuplexClientBase<T>`
	
Callbacks do **NOT** work with `basicHttpBinding`, they require `wsDualHttpBinding`.


##Exceptions in Service

* Left alone or rethrown
    - limited info sent to client - proxy faulted
* Service can throw `FaultException`
    - limited info sent to client - proxy OK
    - client can only catch `FaultException`
* Service can throw `FaultException<T>`
	- client can catch `FaultException<T>` - proxy OK
* `T` can be exception or custom fault contract
    - actually any serializeable type
* `T` must be declared in operation contract
    - included in metadata passed

#Rest Services with WebAPI

*Note: Apparently you can "rest up" a WCF service. WHY?*

* No abstraction of HTTP
	* Bad: Your client needs to know HTTP. BAD? Get real, Mr. Presentor. 
* Totally ubiquitous and interoperable
* Clients of any platform, footprint, or language (Goodby Microsoft).
* MS platform for building true RESTful applications on the .NET Framework
* Rides on ASP.NET MVC
* `ContractNamespace` AssemblyInfo.cs tag

##Routing/Verbs

* [AttributeRouting](http://attributerouting.net/)
	* Available as a NuGet package today, will be baked into MVC 5
* IIS comes with  `PUT` and `DELETE` off by default
* Most .NET devs suck and only use `GET` and `POST`
* `HttpResponseMessage` return and `HttpRequestMessage` parameter to allow testing of full trip HTTP

##Takeaways:
* DI
* Mocking
* Interfaces
* Disappointment
* **ALWAYS** close your proxies, when injected `using (blah as IDisposable)`

#Resources:
* Miguel Castro course on [PluralSight](wwww.pluralsight.com)
* SOA at [Twitter]()
