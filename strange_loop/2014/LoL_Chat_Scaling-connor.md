Scaling LoL Chat
================

To 70 Million Players
---------------------

Presenter: [Michal Ptaszek](http://twitter.com/michalptaszek)

Writer: [Connor Ross](http://twitter.com/otter311)

#### Introduction

In multi-player games communication is super crucial.

Team based game launched in 2009, team vs team.

Chat:

- 1 to 1
- group
- presence - friends, availability, status
- api to create new information from chat data

Stats:

- 67 mi monthly players
- 27 mi daily players
- 7.5 mi concurrent players
- 1 bi events per server per day
- 11,000 messages a second

Components to stable, scalable chat service

- protocol (xmpp)
- server (erlang jabber server)
- data store (Riak)

- honu
- graphite


