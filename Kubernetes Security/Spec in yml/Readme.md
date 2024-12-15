# Section spec in config yml for kubernetes

Spec → 

- securityContext
    - ``runAsNonRoot``: true/false → parameter specifying that the container should run, specifically the container process on a guest with the privileges of a non-root user
    - ``runAsUser`` → start the container with the permissions of the specified user (required in the runAsNonRoot connection to take care of security)
    - ``runAsGroup`` → start the container with the permissions of the specified group (required in the runAsNonRoot connection to take care of security)
    - ``fsGroup`` → paramte to specify the group that will be the owner of the file mounted in the container
    - ``capabilities:`` → drop: - all
    Disables all capabilities in the container, restricting access to advanced system operations.
    - ``seccompProfile:`` → type: RuntimeDefault
    Sets the default Seccomp profile, which restricts the container's access to unsafe system calls.
    - ``allowPrivilegeEscalation:`` → false
    Prevents privilege escalation in processes running in the container.
    - ``privileged:`` → false
    Prevents the container from running in privileged mode, protecting the host system from potential abuse.
    - ``automountServiceAccountToken`` → setting this to false prevents the ServiceAccount token from being automatically mounted to the container, enhancing security by limiting the container's access to the Kubernetes API if it is not necessary.
    - ``serviceAccountName`` → specifies the name of the specific ServiceAccount that the container is to use for authentication and authorization on the Kubernetes API, allowing fine-grained control of the container's permissions.
