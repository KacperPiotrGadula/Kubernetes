# Best practices for state applications

- Using the declarative approach
- Resource limits and forcing (cpu.request, cpu.limit, memory.request, memory.limit)
- Liveness / Readiness
- Specify a specific version of the image (docker image)
- External Storage
    - Chmura: GCE Persistent Disks, Azure Files, Azure Disks, AWS EBS
    - On-prem: NFS, GlusterFS (and others)
- Dynamic volume creation with Storage Class
- CSI storage drivers
- Kubernetes Operator