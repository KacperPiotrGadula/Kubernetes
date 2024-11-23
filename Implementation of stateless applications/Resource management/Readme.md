# Scheduler work:

1. Filtering-which nodes are suitable
to put them under

2. Ranking-that is, the allocation of "points" for selected in the filtering phase Nodes to choose the most optimal nodes for Pod data

# Resource limits
1) Prevent unauthorized consumption of resources
hardware
2) When the container exceeds the specified limit, the container process will be killed
3) If we do not, the container can consume:
- all available resources
- more resources than are available on a given node - at worst case may cause killing of system processes on the node
4) We can specify limits for a given ``namespace``, then the container can use the maximum that is specified in the limit for the entire namespace