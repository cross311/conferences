#Authentication / Authorization Considerations
* Authentication
	* Windows, username/password, cert
	* WS-Federation, SAML 2.0, OAuth2 w/ OpenID Connect
* Token Formats
	* Windows, Basic
	* SAML 1.1, SAML 2.0, JSON Web Token (JWT), SWT (legacy)
* Authorization
	* Roles, Claims, social scenarios and architecture
* Message Protection (TLS / SSL / WS*)
* SecretsController

OAuth1 tried nasty workarounds to get out of having to use SSL. These sucked, and now OAuth2 requires SSL.

Wherever possible choose the lowest common denominator.
* username/password
* social (twitter, facebook, google)

#WebSecurity with MVC
* `[InitializeSimpleMembership]`
* AuthConfig.cs --> Call `WebSecurity.InitializeDatabase`
	* Needs to be early in the pipeline so that it's initialized when called.
* Session-based cookie with all the claims, not just roles
	* `<add name="SessionAuthenticationModule" type="WebApp.Shared.CustomSessionAuthenticationModule" />`
* When using `WebSecurity`, need to call `FormsAuthentication.SignOut()`;
	* `WebSecurity` writes the fa cookie

##POINTS: WebSecurity and Claims
* Initialize WebSecurity early
* Use ClaimsPrincipal to get all claims (Roles)
* Install AuthorizationAttribute as a filter, use AllowAnonymousAttribute to allow unauthenticated access
* Use AuthorizationAttribute to prevent access by roles
* Create utilities to streamline use of claims

##POINTS: WIF Sessions
* Create a custom SessionAuthenticationModule
	* Encapsulate cookie write/delete, ClaimsPrincipal create
* For Forms redirect, need WebSecurity enabled
	* Must delete forms cookie + session cookie
* Other WIF best practices
	* Use SSL
	* Server side session cookies (space, load balancing)
	* Shared token cache (replay detection, load balancing)

##POINTS: Additional WIF Techniques
* ClaimsAuthenticationManager
	* Transform claims from user authentication into application calaims (assumes stored by app)
* ClaimsAuthorizationManager
	* Use with custom AuthorizationAttribute
	* See thinktecture library
* ClaimsPrincipalPermission
	* **DO NOT USE**

##Machine-to-machine handshaking
* Windows auth
* Certificate
* **JWT**

##POINTS: Web API Calls
* **Must authenticate calls to Web API**
* Other stuff in slides

##Social Login and User Consent
* OAuth 2.0
	* Supports variations of passive and active federation
	* Popular for used for user consent flows where an applications wants access to user information from another applications
* Always backdrop to username/password
	* **PEOPLE LOVE SOCIAL, BUT PEOPLE HATE SOCIAL**
* Login or Register? Make it obvious.

#Resources
* Windows Azure Active Directory
	* Sync directories with domain
	* Spin up new dirs
	* Connect with other IdP
* Thinktecture
	* Code base for IdP and Auth Server
	* Fully functional
	* WS-Fed and OAuth2
* http://michelebusta.com
* http://snapboardalpha.cloudapp.net/michelebusta
	* snapboard.com/michelebusta
* michelebusta@solliance.net
* @michelebusta