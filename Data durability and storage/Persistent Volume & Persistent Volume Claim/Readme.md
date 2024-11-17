# Persistent Volume (Access Mode)

- ReadWriteOnce - can be mounted on only one node to
read and write
- ReadOnlyMany - can be mounted on several nodes, but only to
reading
- ReadWriteMany-can be mounted on several nodes, both to
read and write
## Important: a volume can only be mounted by one access type
once at the same time.
## Not every volume driver supports all three types of access

# GCP

## Add persistent volume in GCP

``gcloud compute disks create ps-vol --size 10GB --type pd-standard --zone europe-central2-a``

## Delete persistent volume in GCP

``gcloud compute disks delete ps-vol --zone europe-central2-a``