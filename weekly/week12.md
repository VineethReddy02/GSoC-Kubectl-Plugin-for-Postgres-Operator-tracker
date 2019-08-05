## Calender Week #12 29th July to 04th August

### Summary of work done: 

 - Implemented ```kubectl pg logs -o``` fetches the logs of the operator pod.
 - Implemented ```kubectl pg logs -c CLUSTER -m``` fetches the logs of the master from specifed cluster.
 - Implemented ```kubectl pg logs -c CLUSTER -r 1``` fetches the logs of the master from specifed replica.
 - Implemented ```kubectl pg logs -c CLUSTER``` fetches the logs of the random pod but not master.
 - Improved code quality by removing the code duplication in kubectl pg connect and kubectl pg logs.
 - Enhanced ```kubectl pg version``` with namepace flag.
 - Corrected ```kubectl pg list``` errors.
 - Addressed code reviews comments by folowing code standards.
 
### What can be improved:

- nil

### What went well:

- nil
  
### TODOs for next week

- Review comments need to be addressed.
- Switching to MIT license.

### Backlog

- Autocompleteion of kubectl pg cmds.
- Generation of markdown docs.

