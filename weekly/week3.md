## Calender Week #3: 27th May to 2nd June

### Summary of work done: 

- ```kubectl pg check``` cmd has been implemented by evaluating CRD of name ```postgresqls.acid.zalan.do```.
- Understood internals of postgres operator generated codebase for upcoming weeks work on postgressql objects.

### What can be improved:

 - I was validating ```kubectl pg check``` by the status of postgres operator deployment status. But when i realised crd can be deleted manually and operator status is still running. My initial work fails. I should have done this validations before writing the code.

### What went well:

- Call with my mentor <strong>Sergey</strong>
has clarified by doubts in the beginning of the week.
  

### TODOs for next week

- Create/update/delete of ```kind:postgresql``` i.e ```kubectl pg create/update abc.yaml``` and 
   ```kubectl pg delete abc.yaml/postgresql_name.```
