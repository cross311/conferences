#WCF vs WebAPI:
* WebAPI has killed WCF --> "The report of my death was an exaggeration."
* WCF and WebAPI both have their own uses.
* WebAPI has a much smaller scope and learning curve than WCF.
* One is NOT a replacement for the other
* One is NOT better than the other
* WCF is WAY more feature rich
* Web API is WAY more interoperable
* WCF is based on SOAP protocol
* Web API is based on REST architecture
* WCF DataContracts mirror WebAPI Models

#WCF with WebAPI:
* Write services in WCF and extend with WebAPI

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
* Solution layout
     - Essentials.BusinessEngine
     - Essentials.Client
     - Essentials.Contracts
          - Add System.Runtime.Serialization
          - Add System.ServiceModel
     - Essentials.Host
     - Essentials.Services
          - Services separated from Hosts to allow transport over different avenues (i.e., Not just HTTP).
     - Essentials.WebHost
* ZipCode Database
     
#Resources:
* Miguel Castro course on [PluralSight](wwww.pluralsight.com)
* SOA at [Twitter]()
