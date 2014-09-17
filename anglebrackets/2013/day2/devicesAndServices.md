Devices & Services
===

Presentor: Steve Guggenheimer (@StevenGuggs)

Starts off with a movie clip for AfterLife 3.  Microsoft is going to have a new CEO, Steve is still fully engaged.  Microsoft did a big re-organization putting a lot of different teams together to make developement more fluid.  Aquiring Nokia, deal should close soon.

## Devices

Talked about a lot of the phones that have come out and the new tablets that are trying to do both talet and labtop.

## Windows 8.1

Personalized start and locks screens.  You can run applications from the start screen are now available.  The tile sizes are now more customizable in the os like it is on the phone.  The app snap that was in 8.0 has been completly changed to fully custimizable sizes.  Much more sky drive integration, the phone currently has alot.  Bing is going to be used to navigate the windows store to provide a more personalized experiance.

The new WIndows store ui, is a little less Cosco and more merchendising tools.  Keeps going over how they are changing the ui for the desktop, making it more flat.

## developing for windows

Windows is going to keep going in the touch direction.  Mor eintegration between the store and how your application runs.  A tool that has been created that allows internal organization stores.  Because it is windows a lot of developers already hvae the skills to develop for windows.  Having a common kernal between the phone and the pc is goign to make building application sfor both phone and desktop.  This is going to be continued to be worked on, in bringing them closer.

Windows 8 in the enterprise is going to be expanding.  A quote of, 200 million global informaiton workers would like o use a Microsoft windows tablet for work.

## windows phone

Again shared core between phone and desktop.  The phone xbox and desktop teams in microsoft are now in hte same group.  All the windows platforms are going to have the same ui model, while you might not like it, but it is consistant.  Goal is to make sure that if you write an app for one thing it will work accross the board and devices.  Stating tha twindows has the best consistancy between all devices.

*NOTE: pushBi, Bank of America, Angry birds star wars*

## Apps

Foursquare for tablet first.  They said that widnows 8 has the best place to have a really nice touch based canvus.

Indian Railways.  they choose windows first.  

Vine just come out for windows phone.  Instagram is coming. Temple run.  Slingbox.

# Demos

## Building Apps

Robert Green.  [Khan academy](http://www.khanacademy.org/).  Looking to develop a exercises and quizes section to the windows app just like the web app does.  The way that he does this is by just using full html pages that are just loaded within the app.  so all the quizes have their own html page that has all the html, not templated.

Giving a sneak preview of a web app template.  Really all it does is link to onine content but have it within an app. did not demo having any local storage to make the website work offline.

## Moving a wpf app to windows store app

The application he is demoing is a expense report application written in wpf.  Users of the application want to be able to use the appliation on surface ang on their phone.  What he is suggesting is to mvvm and xaml, those allowing you to use the same service references and some code.  he makes a comment that when he wrote the source code he did a lot of coping a pasting.  For the phone he wants to see if he can get rid of some of that duplication.  What he is recommending is using protable dlls, where you can specify where the libary has to work and it will make sure any of the libraries you use are compatible for all.  Most of this works best if you already have wcf services for the backend to make each of these just work.


## End of device

If you are building a xbox app, it is pretty much the exact same as making a desktop app to start.

# Services

Making a point that to be good at services you should probably run a lot of big services.  Windows runs all of its stuff, bing, cloud drive, xbox live is all on the Azure cloud.  They are eating their own dog food.  It used to be that desktop first, now it is cloud first.  Microsft can allow you to do things in the cloud or in your private data center going back and forth.  