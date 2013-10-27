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

