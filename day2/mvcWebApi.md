Building a Business Asp.Net MVC & Web Forms
===

Presentor: ...

## Demo

Starting off with a mvc bootstrapped application.  Sampling wizard form (process flow).  Sampling a table where you crud an item with differnt pages.  Crud a item using a single page (Most common), grid edit page.  More an overview of what you can do with MVC.

Mentioned that business applications should be boring and safe.  Stick to what is reliable, safe, and works.  User experiance is not as important.  

## Solution Architecture

Use logical layer projects with in the solution.  He says you should keep the Controller forlder in teh front end arch, because else it is hard to tell mvc where all this stuff is.

He has a project business laer that is pretty much just the repository.  It also containes Managers that are repositories...  The idea of using pattern names to him seems unweildy and long names.  Keep your viewMoels dumb so that they do not know what database layer is used.

He also has a configuration class.  This project golds all teh ways to read application settings.  allow of what he is using is ConfigurationManager.

Another project is Framework.  This project contains data access, logging, exceptions, security.  Contains the featrues that any appplication will need no matter what ind of application you are writting.

He does have a test layer, his one example was hitting the database.

Utility project contains base custom wrappers, like a controller.  Put stuff here that are not related to the actuall application just side stuff.  Like wizard handler.

A designated project to just ViewModels.  While this could be used across front ends.  ViewModel stuff however contains more information that is specific to your specific view.

## User Oriented Features

Start off with creating a theme page.  This might start from bootstrap, but you want to copy the base features so that as you change your theme you have a good reference page to look at.  Another suggestion is to create a sample grid that developers can look at for what all needs to be there.  The grid will have paging, edit, delete, create, refresh, sorting.  This example can even be taken to the customer for approval, then as they change it you can see how it changes in teh example.

Second to add onto the theme demo pages, you should also have a demo page that shows how you will do validation and showing of error / validation information.  He is a proponent to having all teh validation on the server, then it is only in one place.  The reasoning for this is the two teir of validation messages, ones on client and ones from server side.

## Using Web Forms Side By Side With MVC

You have all these admin or maintenance pages that are implemented in web forms.  The company does not have time to update of these.  Presentor is mentioning that Web Forms is not going away. Which is kinda funny because that is like saying asembly is not going away because people still use it.

Recommend having a single table for all you lookup information.  This allows you to just have one existing location for adding, editing, ordering lookup tables.

Presentor does not really understand how IIS works with the .Net dlls so that mvc and web forms play well together.  He makes a comment about being able to remove the ignore *.aspx route from teh routing table, however  if you do wildcard mapping this will blow up.  This might also be a feature of the new .net, but anyway he just kinda waved his hands because he does not understand.

Starts talking about mixing permissions and ViewModels.  The idea of having attributes that just ask people for login, does not seem good to him because you dont have context.  I imagine there are ways to pass information to you login page to give more context to display a reason, but that is just a guess.

*Note: Stopping taking notes.  This session is pretty much useless and taught nothing in terms of good practices for migrating between the two.*