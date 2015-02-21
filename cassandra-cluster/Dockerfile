# Cassandra 2.1 Cluster Node Image
#
# VERSION               0.1
#
# Expects CASSANDRA_SEEDS
# If CASSANDRA_SEEDS is not set, node acts as its own seed

FROM cassandra-base

USER root

# Place cluster-node startup-config script
ADD scripts/cassandra-clusternode.sh /usr/local/bin/cassandra-clusternode

# Start Cassandra
ENTRYPOINT ["cassandra-clusternode"]
