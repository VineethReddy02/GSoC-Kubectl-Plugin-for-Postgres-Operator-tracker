## Calender Week #5: 10th June to 16th June

### Summary of work done: 

 - ```kubectl pg list```Lists all the pg resources of the current namespace.
 - ```kubectl pg list all``` Lists all the pg resources across namespaces.
 - ```kubectl pg add-user USER01 -p CREATE,UPDATE,DELETE -c acid-minimal-cluster``` Add a new user and assign roles to it.
 - ```kubectl pg add-db DB01 -o OWNER01 -c acid-minimal-cluster``` Add a new DB along with it's owner.
 - ```kubectl pg ext-volume 2Gi -c acid-minimal-cluster``` To extend the volume.
 
 ### kubectl pg list and kubectl pg list all
 
 ![list-pg](https://user-images.githubusercontent.com/25104868/59565569-091c5000-9073-11e9-96cc-d4e67d4ab03f.png)
 
 ### kubectl pg delete CLUSTER01(enhancement)
 
 ![delete-enhancement](https://user-images.githubusercontent.com/25104868/59565562-f0ac3580-9072-11e9-94e0-cd9a0baec80f.png)
 
 ### kubectl pg add-user
 
 ![add-user](https://user-images.githubusercontent.com/25104868/59565624-82b43e00-9073-11e9-92f9-7d41ff793726.png)

### kubectl pg add-db

![add-db](https://user-images.githubusercontent.com/25104868/59565576-1f2a1080-9073-11e9-964f-2bcb2237353b.png)

### kubectl pg ext-volume

![ext-volume](https://user-images.githubusercontent.com/25104868/59565586-3ec13900-9073-11e9-9908-ded2e43f444c.png)
 

### What can be improved:

- nil

### What went well:

- Right expectations set by ```sergey``` with format of kubectl commands and thanks for ```felix``` for clarifying by doubts quick.
  
### TODOs for next week

- Enhancements on code review comments.
- Documentation.
- e2e test cases for all the work done so far.
- Stabilising the plugin probably for first merge and first evaluation.
