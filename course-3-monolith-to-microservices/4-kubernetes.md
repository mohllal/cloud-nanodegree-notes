# Section 4: Kubernetes

- ***Container Orchestration*** is a logical process of grouping multiple containers into a single virtual entity. This logical grouping helps manage a group of containers that have a similar set of configuration requirements. There are multiple Container Orchestration tools available in the market, such as ***Kubernetes***, ***Docker Swarm***, ***Amazon ECS***, ***Mesos***, and ***Nomad***.

- ***What is Kubernetes?*** Kubernetes (K8s) is an Apache 2.0-licensed open source Container Orchestration tool for effectively managing containerized applications. Kubernetes can automate the deployments, maintaining a logical group of containers, and helps to scale the application services.

- Kuberentes known as Linux kernel of distributed systems.

- One of the main principles of Kubernetes is to decouple the application from the infrastructure:
  - 
  - Automatic scaling up/down based on workload.

- Kubernetes can help in ***managing containerized application*** in the following ways:
  - ***Manage Containers*** - Self-healing such as auto-restart of a backup/replica container in case of a failure, automate the rollouts and rollbacks, configuration management of containers.
  - ***Autoscale Workloads and Load balancing*** - Distributing a load of network traffic to suitable container/node. All services inside Kubernetes are natively load balanced.
  - ***Optimal Resource Utilization*** - Each container has its own resource (CPU and memory) requirements. Kubernetes fits a container to the most suitable Node so that the resources of the Node are utilized effectively.
  - ***Service Discovery*** - Provide native methods for service discovery.
  - ***Storage orchestration*** - Automatically mounting the volumes to containers.
  - Others - Fire off jobs and scheduled ***cronjobs***, quickly integrate and support 3rd party apps, and manage ***Stateless*** and ***Stateful*** applications.

- Kubernetes key components:
  - ***Cluster*** - A set of *Master and Worker* Nodes. When we deploy Kubernetes, we get a cluster, which each cluster has a minimum of one worker node. A master node is capable of managing multiple worker nodes.
  - ***Node*** - A physical or virtual machine that runs multiple containers belonging to an application.
  - ***Master Node*** - A node that decides the pod scheduling, and pod replication. The main components of a master node are - `kube-api-server`, `kube-scheduler`, `kube-controller`.
  - ***Worker Node*** - A node on which pods are scheduled and run.
  - ***Pod*** - A group of tightly coupled containers with shared storage, network, and a specification for how to run the containers. ***All the containers in a Pod are co-located and co-scheduled***. The worker node(s) hosts the pods.

- ***kubelet*** - a ***node agent*** using which the *worker node communicates with the master node*. The `kubelet` runs on each Node.

- ***kube-proxy*** - a ***node agent*** using which the *worker node communicates with the external world*. The `kube-proxy` also runs on each Node.

- ***kube-apiserver*** - the frontend API that exposes the Kubernetes control plane.

- ***etcd*** - a key-value store to stores the cluster state.

- ***kube-scheduler*** - a component that schedules the pods for running on the most suitable Node.

- ***kube-controller-manager*** - a component that bundles and runs controller processes. These processes concern the nodes, replication, endpoints, and access management.

- Tools for deploying the Kubernetes cluster:
  - ***Minikube*** - A lightweight tool that creates a VM on your local machine and deploys a single Kubernetes cluster containing only one node.
  - ***kubectl*** - A command-line utility that allows us to run commands against multiple Kubernetes clusters.
  - ***KubeOne*** - A command-line utility for installing, managing, and upgrading Kubernetes clusters.

- Some Kubernetes beginer commands:
  - `kubectl version`: To display the version of installed Kubernetes client and server.
  - `kubectl version --client`: To display the version of installed Kubernetes cluster.
  - `kubectl config current-context`: To display the configuration file name for the current context.
  - `kubectl get nodes`: To display the list of nodes along with their status, role, age, and version.
  - `kubectl get pods`: To display the list of containers in current namespace.
  - `kubectl get pods --all-namespaces`: To display all pods in all namespaces.
  - `kubectl cluster-info`: To display the cluster state. It returns a URL.

- A pod is a ***logical grouping*** of tightly coupled containers (one or more) that have shared storage, a network, and a standard specification. The worker node(s) hosts *one or more pods* at a time.

- Containers within a Pod have the following essential characteristics:
  - Share the same namespace (IP address and ports), storage, and network.
  - Can communicate within the set using *localhost*.
  - Behaves like a single entity.
  - Will always run on a single host node ***(co-located)*** until the service that they run is terminated. Then, it frees up the resources of the node.
  - will always be scheduled together to run on a host node as a single entity ***(co-scheduled)***. If a container is shut down/added/removed, then the pod has to restart.
  - Uses Docker as the container runtime.
  - Run a single instance of the containerized application. Multiple instances of the application ***(horizontal-scaling)*** can be created by running multiple pods, one for each application instance.

- A ***Controller*** helps to manage multiple pods each running an individual instance of the application. The ***ReplicaSet*** (of pods) ensures the high-availability of the services hosted inside them. ReplicaSets are created and managed by Controller.

- The Controller uses `.yaml` configuration file called ***Pod Template***. It contains the pod specifications such as name, count of replicas, containers to run, port, and many other details.

- Labels are ***tags*** in the form of key/value pairs that are associated with Kubernetes objects (Deployments/Pods). Multiple objects may belong to a single Label. Labeling helps to identify all the objects (and resources) associated with a particular Label.

- Deployment --> ReplicaSet --> Pod --> Container
