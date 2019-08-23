
# GSoC Kubectl Plugin for Postgres Operator tracker
Project tracker for my GSoC project - Kubectl Plugin - for The Postgres Operator.

## Project Abstract
The Postgres Operator is a project to create an open-sourced managed Postgres service for Kubernetes. The Postgres operator manages Postgres clusters on Kubernetes. kubectl plugins enable extending the Kubernetes command-line client kubectl with commands to manage custom resources. The task is to design and implement a plugin for the kubectl postgres command. My project aims to simplify and ease the usage of postgres clusters using the kubectl plugin. As the postgres operator is capable of many features having a kubectl plugin will ease in running the clusters and understanding the resources way better.

## General Info

+ Name: Vineeth Pothulapati
+ Github: [VineethReddy02](https://github.com/VineethReddy02)
+ Email: vineethbfhs@gmail.com
+ Slack nick: Vineeth
+ Mentors: 1. [Sergey Dudoladov](https://github.com/sdudoladov)
           2. [Felix Kunde](https://github.com/FxKu)
           
## Links

+ [GSoC Proposal](notes/gsoc-proposal.pdf)
+ [Project on GSoC website](https://summerofcode.withgoogle.com/organizations/5429926902104064/)
+ [Postgres Operator github repo](https://github.com/zalando/postgres-operator)

## Weekly Summary

### Community Bonding Period - May

+ [Week 0](weekly/week0.md)
+ [Week 1](weekly/week1.md)
+ [Week 2](weekly/week2.md)

### First Phase of Coding Begins...

+ [Week 3](weekly/week3.md)
+ [Week 4](weekly/week4.md)
+ [Week 5](weekly/week5.md)

### Second Phase of Coding Begins...

+ [Week 6](weekly/week6.md)
+ [Week 7](weekly/week7.md)
+ [Week 8](weekly/week8.md)
+ [Week 9](weekly/week9.md)
+ [Week 10](weekly/week10.md)

### Final Phase of Coding Begins...

+ [Week 11](weekly/week11.md)
+ [Week 12](weekly/week12.md)
+ [Week 13](weekly/week13.md)
+ [Week 14](weekly/week14.md)
+ [Week 15](weekly/week15.md)


## Below Pull Request contains all my kubectl pg plugin work
+ [kubectl plugin for postgres operator](https://github.com/zalando/postgres-operator/pull/579#pullrequestreview-275367465)

## Developed Features:

1. Check whether the postgres CRD is registered.

```kubectl pg check```

2. Create postgres cluster using manifest file

```kubectl pg create -f manifest.yaml```

3. Update postgres cluster using manifest file

```kubectl pg update -f manifest.yaml```

4. Delete postgres cluster using manifest file

```kubectl pg delete -f manifest.yaml```

5. Delete postgres cluster using cluster name

```kubectl pg delete cluster```

6. Delete postgres cluster using cluster name in specified namespace

```kubectl pg delete cluster -n namespace```

7. List postgres cluster from current namespace

```kubectl pg list```

8. List postgres clusters from all namespaces

```kubectl pg list -A```

9. Extend volume of an existing cluster

```kubectl pg ext-volume 2Gi -c cluster```

10. Scale the number of instances of postgres cluster

```kubectl pg scale 10 -c cluster```

11. Add a database and it's owner to a postgres cluster

```kubectl pg add-db DB01 -o OWNER -c cluster```

12. Add a user and set of privileges to a postgres-cluster

```kubectl pg add-user USER01 -p login,createdb -c cluster```

13. Fetch the logs of the postgres operator

```kubectl pg logs -o```

14. Fetch the logs of a random replica for the provided cluster

```kubectl pg logs -c cluster```

15. Fetch the logs of master for the provided postgres cluster

```kubectl pg logs -c cluster -m```

16. Fetch the logs of specified replica for provided postgres cluster

```kubectl pg logs -c cluster -r 3```

17. Connect to shell prompt of a random replica for the provided postgres cluster

```kubectl pg connect -c cluster```

18. Connect to shell prompt of master for the provided postgres cluster

```kubectl pg connect -c cluster -m```

19. Connect to shell prompt of specified replica for the provided postgres cluster

```kubectl pg connect -c cluster -r 2```

20. Connect to psql prompt of random replica for the provided postgres cluster, db-user as current user and db-name as current username

```kubectl pg connect -c cluster -p```

21. Connect to psql prompt of random replica with provided postgres cluster, db-user as specified user and db-name as specified user

```kubectl pg connect -c cluster -p -u user01```

22. Connect to psql prompt of random replica with provided postgres cluster, db-user as specified user and db-name as specified db-name

```kubectl pg connect -c cluster -p -u user01 -d db01```

23. Connect to psql prompt of specified replica for the provided postgres cluster, db-user as current user and db-name as current username

```kubectl pg connect -c cluster -p -r 4```

24. Connect to psql prompt of specified replica with provided postgres cluster, db-user as specified user and db-name as specified user

```kubectl pg connect -c cluster -p -r 3 -u user01```

25. Connect to psql prompt of specified replica with provided postgres cluster, db-user as specified user and db-name as specified db-name

```kubectl pg connect -c cluster -p -r 3 -u user01 -d db01```

26. Connect to psql prompt of master for the provided postgres cluster, db-user as current user and db-name as current username

```kubectl pg connect -c cluster -p -m```

27. Connect to psql prompt of master with provided postgres cluster, db-user as specified user and db-name as specified user

```kubectl pg connect -c cluster -p -m -u user01```

28. Connect to psql prompt of master with provided postgres cluster, db-user as specified user and db-name as specified db-name

```kubectl pg connect -c cluster -p -m -u user01 -d db01```


29. Get the version of kubectl pg plugin and postgres-operator in default namespace

```kubectl pg version```

30. Get the version of kubectl pg plugin and postgres-operator in specified namespace

```kubectl pg version -n namespace```
