===========
SSH Tunnels
===========

Convenience tool to create SSH tunnels to cluster applications on AWS.

Example cluster applications would be:

* Kafka
* Zookeeper
* Cassandra

This tool automatically adds the private VPC IPs to your local loopback ``lo`` interface
and to your ``/etc/hosts`` file.
Cluster nodes can be accessed directly from your local machine.

.. code-block:: bash

    $ ./tunnels.py my-senza-stack 9092 odd-eu-central-1.myteam.example.org --region eu-central-1

Usage
=====

Connecting to a Cassandra cluster deployed with Senza:

.. code-block:: bash

    $ piu odd-eu-west-1.myteam.example.org SSH tunnel to Cassandra for keyspace management
    $ ./tunnels.py my-cassandra 9042 odd-eu-west-1.myteam.example.org --region eu-west-1
    # open a new terminal
    $ cqlsh 172.31.141.1 # take one seed IP printed by tunnels.py
