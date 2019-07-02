## Calender Week #7: 24th June to 30th June

### Summary of work done: 

 - Replaced panic error traces with log.Fatal() for better readibility and shorter description on error message.
 - Enhanced with few code review comments. Replaced goto with for, scale and delete pg cmds
   will use the same confirmation loop from util.
 - Enhanced add-user by validating the valid privileges such as 
   {"SUPERUSER", "REPLICATION", "INHERIT", "LOGIN", "NOLOGIN", "CREATEROLE", "CREATEDB", "BYPASSURL"}
 - Now add-user pg cmd can append privilges for existing user. which wasn't supporting before.
 
### What can be improved:

- Connecting to the master and replica pod seems challenging. I am currently working on it.

### What went well:

- nil
  
### TODOs for next week

- Autocompleteion of kubectl pg cmds as per week's agenda.
- Connect to master/replica pod needs to be completed last week but as it's challenging extending it to this week.

### Backlog

- Connect to the master/replica pod shell-prompt/psql-prompt. (currently working)
- Better documentation for kubectl pg tree. glide couldn't retrieve 
  "k8s.io/kubernetes/pkg/kubectl/cmd" 
  "github.com/spf13/cobra/doc" 
  "k8s.io/kubernetes/pkg/kubectl/cmd/util". which are used as dependencies in generating docs. Raised an issue in cobra repo.
- Enhancemens in validations with provided comments from mentors. (Few comments need to be addressed such as minimunInstances,
  Reseserved DBNames and User-Roles from configmap data.) As I don't find the clear labels in configmaps. 
  I am bit confused with this enhancement. 

