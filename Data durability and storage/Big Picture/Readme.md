# Ephemeral volumes

-> ephemeral - in other words,ephemeral."
-> The data is stored for as long as the Pod exists
-> In other words: when Pod is removed-volumen also
-> Most often these are local volumes (data stored on the node where Pod is launched):
1) EmptyDir
2) ConfigMap
3) Secret
4) CSI ephemeral volumes (about this in the following lessons)