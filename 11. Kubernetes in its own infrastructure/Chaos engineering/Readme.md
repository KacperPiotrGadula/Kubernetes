# Configuration run time kubemonkey
```
apiVersion: v1
kind: ConfigMap
metadata:
  name: kube-monkey-config-map
  namespace: kube-system
data:
  config.toml: |
    [kubemonkey]
    run_hour = 11
    start_hour = 12
    end_hour = 13
    blacklisted_namespaces = ["kube-system"]
    time_zone = "Europe/Budapest"
    [debug]
    enabled = true
    schedule_immediate_kill = true
```