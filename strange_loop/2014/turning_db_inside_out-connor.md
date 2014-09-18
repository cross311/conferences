Turning the DB Inside Out With Samza
====================================

Presenter: [Martin Kleppmann](http://twitter.com/martinkl)

Writer: [Connor Ross](http://twitter.com/otter311)

### Introduction

Talk about database arch and application arch.  Apache Samza.  Designing data-intensive applications.  dataintensive.net

### Core

Stateless backend, but it all gets pushed into the database.  The mutable global state, something if we wrote it in our app we would try and get rid of it, but still doing it with databases.  IT HAS ALWAYS BEEN THAT WAY?

- Replcation
  - Ends up using immutable state to send to the slaves to say something was updated.
- Secondary Indexes
  - creates secondary views and keeps them up to date
- Caching
  - Managed in application code
  - Race conditions
  - Cold start
- Materialized Views
  - a pre executed view that is stored on database
  - magically auto updating cache

^^^ DERIVED DATA ^^^

what if we take a replication log and make that the public api.  Apache Kafka.  Not really queryable.
 
If we consume it and turn them into materialized views.  stream processing.  Apache Samza (incubater)
 
Want to add a new view, just go back to the beginning of time and compute the view.  Kapa architecture.
 
Interesting things

- Better data
  - breaks apart reading and writing
  - normalizing limit is how good you want reading to be, this gets rid of this
  - good for analytics
  - write once, read from manay different views
  - historical point-in-time queries
  - recovery, bad code deployed
- Fully precomputed cache
  - no code cache
  - better isolction/rebustness
  - no hit/miss rate
  - no race conditions
- Streams everywhere!!

Rethink request -> response

to Subscribe -> Notify

STREAMS EVERYWHERE!!!

TS2014 -> dataintensive.net

samza.incubator.apache.org

for log compaction. Assigns a key and only keeps the latest version after a certain date.