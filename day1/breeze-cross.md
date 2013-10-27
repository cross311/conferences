Breeze.js
===

Presentor: Ward Bell (@wardbell)

* Presentation: AngularJs
* Data Management: Breeze

Quote: *Make Ajax calls adn bind the results*

$http from angularjs is merely access to json data. Do you need to do anything more?

## Questions

One type or multiple types?  Todo?  Customer, Supplier, Orders, Shippers.  In real life you dont just have one type.  They are related and they need to be managed together.

How much do you pull?  How much of the graph to do follow?  When do you pull down items from the graph?  This seems like you are just going to be pulling the whole database if you dont do this write.

Is any of the data that your are retrieving static?  How often do you really need to update this information on your application?  You would like to be able to cache some of the stable data.  If the data is supper stable maybe you want to be able to prefetch and cache.

Multiple views use the same object?  How do i use the same object across all these controllers?

Do I save data immediately, or do I wait to save the data?  If I dont save it immediatly, how do I know what to save and what not to save?

What about if I want to have a single transaction across a number of objects?  How do I do this on the client, I know how to do this on the server.  What about if they want to rollback??

## Query

Breeze lets you try and do linq for the client side.  EntityQuery that you can run on a EntityManager that will fail or succeed.

```js
var query = EntityQuery.from('Speakers') // service endpoint
			.where('lastname', 'startsWith', 'S') // filter on server side
			.orderBy('firstName, lastName') // order by on server side
			.select('id, firstName, lastName, imageSource') // select limited fields on server side
			.skip(...).take(...)
			.using( ... queryStrategy.local? ...); // you can have things cached
```

Turns this into an OData-query URL

```
http://localhost:8080/breaze/Breaze/Speakers?
$filter=startswith(LastName,'S') eq true&
$orderby=FirstName,LastName&
$select=Id,Firstname,ImageSource
```

Have server side code for .Net and Mongo.  A good place to learn about this: [Learn Breeze](http://learn.breezejs.com).

