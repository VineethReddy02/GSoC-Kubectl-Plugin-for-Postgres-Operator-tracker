## Calender Week #8: 1st July to 7th July

### Summary of work done: 

 - Enhanced KUBECONFIG validation to check in environment variables as well. Because kubectl searches for env variables and for a 
   KUBECONFIG file in ~/.kube/config.
 - MIN_INSTANCES & MAXINSTANCES are validated from configmap & operatorconfiguration before scaling.
 - ```kubectl pg connect -c CLUSTER01 -m``` This commands connects to the master of provided cluster.
 - ```kubectl pg connect -c CLUSTER01 ``` This commands connects to the random replica of provided cluster.
 - ```kubectl pg connect -c CLUSTER01 -r REPLICA_POD_NAME ``` This command connects to the provided replica pod 
   of provided cluster.
 
### What can be improved:

- nil

### What went well:

- nil
  
### TODOs for next week

- Connect to psql prompt.  
- Autocompleteion of kubectl pg cmds.
- Generation of markdown docs.

### Backlog

- Review comments need to be addressed. 

