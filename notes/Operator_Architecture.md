
### Spilo 

Spilo is a Docker image that provides PostgreSQL and Patroni bundled together. Patroni is a template for PostgreSQL HA. Multiple Spilos can create a resilient High Available PostgreSQL cluster. For this, you'll need to start all participating Spilos with identical etcd addresses and cluster names.

### Patroni

- Automatic failover solution for PostgresSQL
- A daemon that manages one PostgresSQL instance.
- Keeps the state of the cluster in a DCS(Distributed consistency store) (Etcd, Zookeeper, Consul, Kubernetes), also refered to as a consistency layer.
- For new instances decisions whether to initialize a new cluster or join an existing one.
- For running instances executes promotion/demotion when necessary.
- A number of additional related functions(global configuration, scheduled actions, pause mode, pg_rewind support etc)

Patroni is attached to every instance of postgres it takes care of promotion if it is a worker and demotion if it's master.
Every replica looks at the neighbours and leader assess how far it is away from them. Based on it's performance it acquires the lock from etcd to become the leader.

- Operator starts pods with Spilo docker image
- Operator provides environment variables to spilo.
- Operator makes sure all kubernetes objects are in sync.
- Spilo generates patroni configuration.
- Patroni creates roles abd configures PostgreSQL.
- Patroni makes sure there is only one master.
- Patroni uses k8s for cluster state and leader lock.
- Patroni creates roles and applies configuration.
- Patroni changes service endpoints on failover.

![Screenshot (11)](https://user-images.githubusercontent.com/25104868/58109276-f72dc580-7c0a-11e9-9725-c22c2f038121.png)
