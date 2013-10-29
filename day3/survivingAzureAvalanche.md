Surviving the Azure Avalanche
===

Presentor: Michele Leroux (@michelebusta)

## Compute

Compute section is actually three different choices: VMs, Cloud Services, Web Sites.

### Virtual Machine

The normal provisioning style where you choose the OS, you upgrade it, you install stuff.  Cloneing and backup is easy with blob storage.  This is closest have having the machine completely dependant on you.

### Web Sites

Free -> Multi-tenant daily quotas

Shared -> Multi-tenant. no quotas

Reserved -> dedicated VMs. no quotas.  This is not one vm per website this is one vm per region for many or your accounts websites.

Supported Frameworks: .net, asp, php, node.js

Supported Publishing Methods: ftp, web deploy, git, tfs

### Cloud Services

A container of related service roles: Web role or worker role.  You can set them up to all run on one vm or across many vms it is configurable.

Gotcha: Do the deploy on the cloud project

Deployment: (Service artifacts, model) => .cspkg, (config) => @.cscfg.  Gets sent to azure each of the cspkg get put on the vms behind the LB.  Not copying files, it just builds the files into a slug.  You can also switch a staging and production environment after the staging gets the new code then the LB just switches over.  This also just allows you to switch back.

### Compare

Check out her slide share to get a really good picture of the comparision.

She is almost saying tell me why I should do a cloud service compared to a web site.

What will make me switch to cloud services
* IIS Settings
* Dynamic DNS
* Internal Endpoints
* Async Workers (windows service)
* Vertual network
* RDP (not a good argument)
*  Non-http protocals
*  OS Updates control
*  Certificate Store Access

*Note: firewall rules for websites are based off of ips not cloud type, this will add a bunch of firewall work if a node ever switchs node*

Websites are pretty much first class citizens.

## Data

SQL db has a 150GB limit.  1Tb limit if you do SQL Server on Azure VM.

HDInsight aggragation of data across domains.  Dont drink the Koolaid!  Lynn Langit (contagiouscuriosity.com)

## Networking

Virtual networks: works with virtual machines and cloud services.

Traffic manager: load balance endpoints is really for managing traffic across regions.

## Caching

Co-Located Caching allows you to leverage systems that you already have provisioned.  You can also do shared Caching that will allocate worker roles for caching that migrates caching information across worker nodes.

## Messaging

Service busses can be used to punch a hole in your firewall to on premise data.  Service Bus can also use certificates for sequring. Relay..

Queues talk was just a basic definition of queues.  Topics are also available with pub sub.