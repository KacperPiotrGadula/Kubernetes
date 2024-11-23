# The initial stages of life pods

## Pending
Pod is waiting for a signal from the scheduler, on which node to be created

## ContainerCreating
Under was placed on a specific
nodes, container (s) are running

## Running
At least one of the containers is still working.,
or its main process starts/restarts

# Pod conditions

## PodScheduled
Under assigned to noda

## Initialized
InitContainers have been launched

## ContainersReady
All containers are working.

## Ready
The app is working -> ready accept user traffic

# Readiness Probe

Make sure the app is ready to accept traffic
users

# Liveness Probe

- To prevent this, when designing applications (most often) a special HTTP endpoint is created that can be cycled filed to: ``/health`` or ``/healthz``
    -> Regardless of whether the application was designed under Kubernetes

# Important: both liveness and we define readiness for containers