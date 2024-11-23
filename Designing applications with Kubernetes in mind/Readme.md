# Clouad Native Computing Foundation (CNCF)

Technologies around Kubernetes E.g.

1) Prometheus
2) Helm
3) Open Policy Agent
4) Harbor
5) ContainerD
6) Argo
7) CRI-O


# Cloud Native Aplication

Application developed for: 

1) Cloud
2) On-premise
3) Privete cloud
4) Hybrid cloud

# Cloud Native is not just microservices

1) Containers, thanks to which we can run applications in
any infrastructure

2) Patterns, such as the Twelve-Factor App

3) Container orchestration, which is necessary with a large
number of containers

4) Microservices (yes, microservices are also one of the
cloud native foundations, but not the only one)

5) Backend services (databases, caches, queues, monitoring,
analytics)

6) Automation, classic CD / CD and GitOps approach


# Stateful vs. stateless applications

Sessions        |       No ssession
Login           |       No login
Basket          |       No Basket
Dynamic Content |       Static Content

# 12 Factor

## I Codebase
Single source code tracked by version control system, multiple implementations

## II. Dependencies
Explicitly declare and separate dependencies

## III. Configuration
Store configuration in the environment

## IV. Support services
Treat support services as allocated resources

## V. Build, publish, run
Separate the build and launch phases

## VI. Processes
Run the application as one or more stateless processes

## VII. Port allocation
Make services available by assigning ports

## VIII. Concurrency
Scale through appropriately sized processes

## IX. Transferability
Increase flexibility by allowing applications to start and stop quickly

## X. Uniformity of environments
Keep the configuration of environments as similar as possible

## XI. Logs
Treat logs as a stream of events

## XII. Application management
Run administrative tasks as one-off processes

# Importnat

-> not every application is suitable to be hosted in a kubernetes environment

-> kubernetes is not a cure for challenges