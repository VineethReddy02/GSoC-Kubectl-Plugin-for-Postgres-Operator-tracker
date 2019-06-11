## Calender Week #4: 3rd June to 9th June

### Summary of work done: 

-  ```kubectl pg create -f minimal-postgres-cluster.yaml``` command has been implemented to create postgresql resources.
-  ```kubectl pg update -f minimal-postgres-cluster.yaml``` command has been implemented to update postgresql resources.
-  ```kubectl pg delete -f minimal-postgres-cluster.yaml``` command has been implemented to delete postgresql resources.
-  ```kubectl pg delete -n acid-minimal-cluster``` command has been implemented to delete postgresql resources using object name.
![Screenshot (22)](https://user-images.githubusercontent.com/25104868/59260050-88b3b480-8c58-11e9-8bf8-b6ae3dfd371e.png)

Note: The above image represents ```kubectl pg``` as ```kubectl-pg``` as windows has some issues it says "not supported by windows". Usaually it works as ```kubectl pg``` in all linux machines. 

### What can be improved:

- Testing from my side after implementation can be improved. I keep noticing some cases failing once in a while for no reason.
- Not sure why sometimes postgres-operator gets into a state of error and CrashLoopBackOff during updaton and during deletion
   some times I find postgresql resource being deleted but pods remain to stay as orphaned.

### What went well:

- nil
  
### TODOs for next week

- list command to list postgresql not sure what fields need to be shown such as name, age etc..
   ```kubectl pg list```
- Add space,users,DBs explicitly using kubectl pg commands.
