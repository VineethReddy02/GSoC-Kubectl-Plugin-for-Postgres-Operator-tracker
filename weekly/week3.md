## Calender Week #1: 27th May to 2nd June

### Summary of work done: 

- ```kubectl pg check``` cmd has been completed.
- ```Understood internals of postgres operator generater codebase.

### What can be improved:

 - I was validating ```kubectl pg check``` by the status of postgres operator deployment status. But when i relaised crd can be deleted manually and operator status is still running. My initial validation work fails. I should have done this validations before writing code.

### What went well:

- Call with my mentor ####Sergey has clarified by doubts in the beginning of the week.
  

### TODOs for next week

- Create/update/delete of kind:postgresql i.e ```kubectl pg create/update abc.yaml```
  and ```kubectl delete abc.yaml/postgressql_name.```
