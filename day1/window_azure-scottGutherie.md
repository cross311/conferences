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

### Websites

Build with asp.net, node.js, php.  Deploy in seconds with ftp, git, or tfs.  To create the website through the management dashboard took around 5 seconds.  Created a default web app and did a visual studio publish setting.  You can choose from a drop down of azure spun up applications.  Took around 4 seconds for a full asp.net mvc appliaction to the azure cloud.  Everyone gets 10 free web sites for life!  The dashboard for the machine in azure gives you cpu time, data in, data out, http server errors, requests.  The web analytics was pretty much in real time.  The free teir is about 150 thousand requests a day.  In the standard web site mode you can run more then one application on the same machine to limit the price for the machine since you get a pure vm to you.

Azure uses a deployment service to handle the deployment of new application updates to the actual machines that are running the application.  The deployment is not handled on the instance machine.  The website service is very opinionated to use best practices.  

### Auto Scaling

They offer Auto scaling so that peak load you have more servers, allowing better utilization and less money.

Offer Auto scalling for cpu utilization, queue size, and some other server metrics.  Claiming 60 to 80 percent savings from having running your normal machine count.  You can also setup pre-warming based on a schedule, day time, night time, certain day.

### Logging and Telemetry

New Visual Studio allows you to stream logs to your local machine in real time.  He used System.Diagnostics trace statement.

There is a new feature called developer analytics, that allows you to select different providers.  The one he demos is NewRelic.  He installs the NewRelic package onto his site view the nuget package manager.

### HDInsight (Hadoop)

Can create a cluster from the Azure dashboard.  The dashbaord shows how many tasks are running.  Guthie goes over pretty much what hadoop will be good to use for.

Giving a oversight how Microsoft is actually using azure.  Games are an example of what they are doing, some of the virtual worlds are deployed on Azure.  Halo 4 is using the hadoop cluster to track gamepplay quality, user behavior, etc by time.  Short timeline, small team, not hadoop experts.  Halo 4 stores small bits of data are logged to azure in blob storage.  Runs the data through a stripper of pii.

Excel now has a plugin that is free that allows you to pull data in from HDFS and Azure HDInsight.  First split by delimeter then first row as headers.  Changes the type of a few of the columns to match what the actual types are, like date or int.  Does not just download the whole amount of data, that would be bad.  After you figure out how you want to download it, it brings down around 1000 rows.  Uses another excel plugin called Power Map that can put geo data onto a map within excel.  Start by picking the column that is the geo location, he chose states.  Then you choose what you want to layer it with, he chooses avg number of minutes that the user plays. (INSERT IMAGE FROM PHONE).  He then compares length of game play and number of weapons used (INSERT IMAGE) and notices that this is not really a factor for keeping people play.  However if you look it at how many people you play with, makes you play longer.


### Active Directory

You can now run active directory in the cloud that can allow be synced with your corperate active directory.  Active directories in the cloud are free!  If you want to keep your corp active directory synced with Azure, a downloadable tool is easily intalled to keep the two synced.  Also comes with cloud based Multi-Factor authentication out of the box.  However Mult-Factor is not included free!  But all the other parts of Active directory are all free.

### Other

* Big data
* database
* storage
* traffic
* cloud services
* caching
* messaging
* identity
* web
* mobile
* media
* cdn
* biztalk

*Note: MSDN save quite a bit of money on Azure services.  All around 90%*

As a developer with a msdn license you get up to $150 a month.  They will also auto turn things off if you hit your spending limit.

[Friday With Azure](http://friday.azure.com)