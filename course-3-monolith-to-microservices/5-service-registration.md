# Section 5: Service registration

- Kubernetes has an integrated pattern for decoupling configuration from application or container. This pattern makes use of two Kubernetes components: ***ConfigMaps*** and ***Secrets***.

- What is ***ConfigMap***?
  - Externalized data stored within kubernetes.
  - Can be referenced through several different means:
    - environment variable
    - a command line argument (via env var)
    - injected as a file into a volume mount
  - Can be created from a manifest, literals, directories, or files directly.

- What is ***Secret***?
  - Functionally identical to a ConfigMap.
  - Stored as `base64` encoded content.
  - Encrypted at rest within `etcd` (if configured!).
  - Ideal for ***username/passwords***, certificates or other sensitive information that should not be stored in a container.
  - Can be created from a manifest, literals, directories, or from files directly.

- A pod can use a Secret in either of the following two ways:
  - As files in a volume mounted on its containers.
  - ***kubelet*** uses secrets while pulling images for the pod.

- There are 4 major service types:
  - ClusterIP (default)
  - NodePort
  - LoadBalancer
  - ExternalName

- What is Services?
  - Unified method of accessing the exposed workloads of Pods.
  - Durable resource (unlike Pods):
    - Static cluster-unique IP
    - Static namespaced DNS name
  - Target Pods using equality based selectors.
  - Uses ***kube-proxy*** to provide simple load-balancing.
  - *kube-proxy* acts as a daemon that creates local entries in the host’s *iptables for every service*.

- `kubectl scale deployment/user --replicas=10` command is used to scale the ReplicaSet up.