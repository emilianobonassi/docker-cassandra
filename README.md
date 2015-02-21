Cassandra in Docker
===

This repository provides everything you need to run Cassandra in Docker, and is tuned for fast
container startup. 

Based on java/oracle-java7 (Ubuntu) .

Version of Cassandra is 2.1.2 .

Why?
---
While naive Cassandra images take around 30 seconds to start, our containers take only a few seconds.
Optimizations include:

* Disabling something called "waiting for gossip to settle down" because there is no gossip in a
  one-node cluster (another ~10 sec).

In the box
---
* **emilianobonassi/cassandra**

  This is probably the image you want, it runs a one-node Cassandra cluster.
  Built from the `cassandra` directory.

* **emilianobonassi/cassandra:cluster**

  Runs a Cassandra cluster. Expects `CASSANDRA_SEEDS` env variable to be set.
  If `CASSANDRA_SEEDS` is not set, node acts as its own seed. Built from the `cassandra-cluster` directory.

* **emilianobonassi/cassandra:base**

  The base image with an unconfigured Cassandra installation. You probably don't want to use this
  directly. Built from the `cassandra-base` directory.