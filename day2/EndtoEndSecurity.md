#End-to-End Security For Your Web API and MVC Applications
#### Michele Leroux Bustamente - Monday 3:30-4:30

### Intro
- Tons of standards still in the process of being centralized, leading to half-baked implementations and disparity in protocols.
#### Considerations
- Authentication: Windows, username/pass, cert, WS-Federation, SAML 2.0, OAuth 2 w/OpenID
- Token Formats: Windows, basic, SAML, JSON Web Token, SWT
- Authorization: Roles, Claims, social scenarios and architecture
- Message Protection: TLS/SSL/WS*
> "At the end of the day, people are favoring less complexity because SSL is 'good enough.' "

### Architectural factors
- Multi-platform applications tend to prefer social logins (better for form-factor, already baked into the devices)
- WPF applications can use OAuth/SAML; very well-understood implementation
- Wherever possible choose the lowest common denominator

### MVC 4/Web Security
- Basic template hooks up forms authentication automatically
- This gives you web security and forms authentication.
- But, you want a session based cookie that gives you claims so you can hold more detailed claims info.
- Best practice to call `InitializeDatabaseConnection()` in AuthConfig so it gets hit as early as possible. Otherwise, lookups on roles are not possible.
- After calling WebSecurity.Login, should grab roles off it and put roles on the Claims Principal. Using a role claimtype will support other default role-based functionality if no additional customizations are made.
- Install AuthorizationAttribute as a filter, use AllowAnonymousAttribute.
- Use AuthorizationAttribute to prevent access by roles
- On signout, need to delete both the session cookie and the forms authentication cookie.
 - This is because you can't turn FormsAuth off in order to use WebSecurity and so you're writing two cookies.
- Other best practices:
 - Use SSL
 - Server side session cookies (space, load balancing)
 - Shared token cache (replay detection, load balancing)
- Additional techniques for WIF:
 - Transform claims from user authentication into application claims using ClaimsAuthenticationManager
 - ClaimsAuthorizationManager for use with custom AuthorizationAttribute -- see ThinkTecture library (FOSS)
- Don't use ClaimsPrincipalPermission for MVC

### Web API
- Typically back end servers don't care who the user is, but frequently passing along some information about the user is unavoidable. Thus it's important to pass the claims along.

### Social Login and User Consent
- OAuth 2.0 supports variations of passive and active federation; ie Twitter granting access rights for specific things

### Tools
- Windows Azure AD
 - Sync directories, spin up new directories, connect with other IdP
- Thinktecture
 - Code base for IdP and Auth Server, fully functional, WS-Fed and OAuth2, SAML2 comin
- Auth0
 - Closed source 

Can check out SnapboardDemo for social login code.
Conference resources at michelebusta.com
 
 