# Persistent Volume (Access Mode)

- ReadWriteOnce - can be mounted on only one node to
read and write
- ReadOnlyMany - can be mounted on several nodes, but only to
reading
- ReadWriteMany-can be mounted on several nodes, both to
read and write
- Important: a volume can only be mounted by one access type
once at the same time.