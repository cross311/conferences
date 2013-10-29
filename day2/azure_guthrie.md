#Azure:
* Databases
* VMs
* automation
* open (Windows, Linux, VS.NET, other languages)
* Regions (a la AWS)
* API is consistent across regions (YAY?)
* Everything configured through code, all remote...what about MessageBoxes?
* A la carte licensing
* Availability sets - separate servers, racks, power supplies
	* Automatic load-balancing, if X attempts fail, remove from public rotation
		* New instance of application is spun up on new VM on failure
* S2S VPN tunnels allow tieing cloud machines into your VPN.
	* Can be done over public internet or leased Fiber line.
	* Tunnels can be site-to-site (office to cloud) or point-to-site (specific machine to cloud)
	* Download VHDs locally
* PRETTTTTTY Graphs
* Copy/Paste connection strings for DBs
* auto-scaling
* 

#Command Line Automation
* Will be built into Visual Studio
	* Right in the Server Explorer
* Everything is scriptable through PowerShell
	* Simple (?) PowerShell scripts
* Script Center on Azure site with examples (YAY).
