## Calender Week #13 05th August to 11th August

### Summary of work done: 

 - Addressed code reviews comments by folowing code standards.
 - Considering better code readability specificed spaces between logical code blocks.
 - Fixed bug for ```kubectl pg ext-volume 13 -c acid-test-pg-plugin``` right now it asks to specify valud volume units.
 - Fixed bug for ```kubectl pg add-db test-db -o test-user -c some-test-db-name```
   this will not raise nil map exception. Irrespective of datatbases defined in cluster manifest user can add them.
 - Swicted update to patch in ```kubectl pg scale``` to avoid some default value show up in
 ```kubectl describe postgresql``` but this doesn't seem to work.
 
### What can be improved:

- nil

### What went well:

- Sergey planning for a weekly call twice a week made few things work in fatser iteration.
  
### TODOs for next week

- Licensing needs to be addressed.
- Auto build version enhancement for kubectl-pg plugin.
- Getting ready for final evaluation.



