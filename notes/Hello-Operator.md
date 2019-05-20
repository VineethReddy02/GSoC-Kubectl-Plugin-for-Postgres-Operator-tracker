#### ConfigMap is used to store the configuration of the operator

```
    $ kubectl --context minikube  create -f manifests/configmap.yaml
```
  
####	First you need to install the service account definition in your Minikube cluster.

```
    $ kubectl --context minikube create -f manifests/operator-service-account-rbac.yaml
```
  
#### Next deploy the postgres-operator from the docker image Zalando is using:

```
    $ kubectl --context minikube create -f manifests/postgres-operator.yaml
```
  
####	Check if CustomResourceDefinition has been registered
  
```
    $ kubectl --context minikube   get crd
```
	
#### Create a new Spilo cluster

```
    $ kubectl --context minikube  create -f manifests/minimal-postgres-manifest.yaml
```
  
#### Watch pods being created

```
    $ kubectl --context minikube  get pods -w --show-labels
```
  
#### Connect to PostgreSQL
 
We can use the generated secret of the postgres robot user to connect to our acid-minimal-cluster master running in Minikube:

```
    $ export HOST_PORT=$(minikube service acid-minimal-cluster --url | sed 's,.*/,,')
    $ export PGHOST=$(echo $HOST_PORT | cut -d: -f 1)
    $ export PGPORT=$(echo $HOST_PORT | cut -d: -f 2)
    $ export PGPASSWORD=$(kubectl --context minikube get secret postgres.acid-minimal-cluster.credentials -o 'jsonpath={.data.password}' | base64 -d)
	  $ sudo apt-get install postgresql-client
    $ psql -U postgres
 ```
   ### List of objects created 
```
vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get pods
NAME                                READY   STATUS    RESTARTS   AGE
acid-minimal-cluster-0              1/1     Running   0          26m
acid-minimal-cluster-1              1/1     Running   0          25m
postgres-operator-ff9459df6-9gmp4   1/1     Running   0          31m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get deployments
NAME                READY   UP-TO-DATE   AVAILABLE   AGE
postgres-operator   1/1     1            1           32m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get crds
NAME                        CREATED AT
postgresqls.acid.zalan.do   2019-05-20T18:29:18Z

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get statefulsets
NAME                   READY   AGE
acid-minimal-cluster   2/2     2m13s

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get serviceaccount
NAME                        SECRETS   AGE
default                     1         57d
zalando-postgres-operator   1         39m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get secrets
NAME                                        TYPE                                  DATA   AGE
default-token-c5rnj                         kubernetes.io/service-account-token   3      57d
foo-user.acid-minimal-cluster.credentials   Opaque                                2      28m
postgres.acid-minimal-cluster.credentials   Opaque                                2      28m
standby.acid-minimal-cluster.credentials    Opaque                                2      28m
zalando-postgres-operator-token-9tlxn       kubernetes.io/service-account-token   3      39m
zalando.acid-minimal-cluster.credentials    Opaque                                2      28m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get configmap
NAME                DATA   AGE
postgres-operator   32     41m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get persistentvolumes
NAME                                       CAPACITY   ACCESS MODES   RECLAIM POLICY   STATUS   CLAIM                                   STORAGECLASS   REASON   AGE
pvc-0dfd9af5-7b2e-11e9-b345-080027e169be   1Gi        RWO            Delete           Bound    default/pgdata-acid-minimal-cluster-1   standard                27m
pvc-cb7dcc76-7b2d-11e9-b345-080027e169be   1Gi        RWO            Delete           Bound    default/pgdata-acid-minimal-cluster-0   standard                29m

vineeth@vineeth-Lenovo-Z51-70:~$ kubectl get clusterrolebinding
NAME                                                   AGE
zalando-postgres-operator                              49m

vineeth@vineeth-Lenovo-Z51-70:~/go/src/github.com/zalando/postgres-operator/manifests$ kubectl get clusterrole
NAME                                                                   AGE
zalando-postgres-operator                                              52m

```
