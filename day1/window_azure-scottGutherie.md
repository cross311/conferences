Windows Azure
===

Presentor: Scott Guthrie

Introduction by .Net Rocks!  They are trying to get people to participate in [Humanitarian Toolbox](http://www.htbox.org/)

Quick sales pitch: Flexible | Open | Consistent

Number of data centers: 29, all over the world that are exposed via regions.  Looks similar to AWS with regions but there are quite a bit more.  Showing a video of the data centers, that are pretty much just containers like the old Sun rooftop data center.

### billing

Like AWS if you stop the vm you do not pay for it.  All billing is based on minutes of use.

## Demo of Azure Management

Starts off by creating a virtual machine.  The default choice of images is quite large and very microsoft.  They also offer the base ubuntu and *nix boxes.  There are a small number of size choices.  One thing that is nice compared to AWS is actual named dns for outside the azure arch.  HAHAH for all those who are used to medistrano, their rdp download actually work.  Did a here is a cake I baked earlier, so did not really see how long it takes to spin up a base node.  Update: it seemed to take around 20 minutes.

Their idea of load balancing actually forces machines in the same availability set are on different racks and not under the same router.  Availability sets are choosen using a drop down, this seems like it would be really bad for our company.  Only demoed pinging on tcp for up, I imagine that you can still do http endpoint.

The network control seems to be a bit more then AWS.  It talks about using many subnets and secure tunnels, almost like you were the one making the network.  You can also setup a fiber lease line, which seems awesome.  Talks about being able to setup a site to vpn endpoint for your azure private network.  There is a download vpn client right on the website, nice!  Demod the site to vpn, however did not show how he added the personal cert for the developer machine.

Talks about doing automation through the command line, and talks about doing azure control via visual studio.  Also showing how to remote powershell into a box and remotely install iis.  The command line file was quite long.  They do have a script center that seems like it has a good number of scripts to start off with.

Talks about moving Azure management into your own data center.  Allowing you to use the same gui that a developer would use for public Azure on your local DC, must have msServer 2013 R4.

## Platform as a Service

### Sql Database

Comes clustered, fully managed service.  Creates a database during the presentation to prove how long it takes for it to spawn up, it took about 5 seconds.  The dashboard that comes with the managed sql, shows a graph for deadlocks, failed connections, successful connections. Do not have to worry about patching, and it is managed with 3 different dbs on different servers.  Demoed scaling up to a 150 db database from 1 gb took around 4 seconds.  You can automatically setup a database backups, and you can add saving to a storage account that will force a distance of really far away.