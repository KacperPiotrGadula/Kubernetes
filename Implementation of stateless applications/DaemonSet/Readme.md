# ReplicaSet vs DeamonSet

## ReplicaSet
- take care of a certain number of pods, no matter what node
- Application: business applications

## DaemonSet
- run one pod on each node
- Application: tools/services supporting business applications and / or cluster operation

# DeamonSet

Important: DaemonSet is not
the direct mechanism for
deploying stateless applications,
but it can be an addition
(e.g. monitoring, logs)