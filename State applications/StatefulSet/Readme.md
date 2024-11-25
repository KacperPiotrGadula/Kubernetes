# Deployment vs StatefulSet

```
Deployment                          StatefulSet
1. Pods can be created"at once"     1. Pods created sequentially, one by one
2. Random names of pods at first    2. Constant numbering of pods-both
creation, as well as                   during the first creation, as well as
scaling/modifying                      scaling/modifying
3. One PersistentVolumeClaim for    3. Each replica has its own,
all replicas                           dedicated PersistentVolumeClaim
4. If any sub is deleted,           4. If any sub is deleted
a pod with a different name            in its place will be added a sub
will be added in its place             with exactly the same name

```
