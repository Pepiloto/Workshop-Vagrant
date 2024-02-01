# Epitech Workshop Vagrant - Part 2

## Let's start with context

For this part you'll have to create a Kubernetes Cluster with Vagrant.

### The specs

Type | Number | CPU | RAM | Names | IP
--- | --- | --- | --- | --- | ---
Master | 2 | 1 | 1024Kb | Kubemaster1, Kubemaster2 | 10.0.0.11, 10.0.0.12
Worker | 4 | 1 | 512Kb | Kubenode1, Kubenode2, Kubenode3, Kubenode4 | 10.0.0.21, 10.0.0.22, 10.0.0.23, 10.0.0.24
Load Balancer(Traefik) | 1 | 1 | 512Kb | Traefik | 10.0.0.30

OS: generic/alpine312

Vagrant plugins to install: vagrant-relaod, vagrant-vbguest

[Here](hosts.yaml) is the hosts.yaml file.
It contains the specs of the cluster.

The scripts are interesting too, you can find them [here](scripts).
You should look at them.

To use the Kubernetes API from your local host you must execute the finalize_setup.sh script. This script will also export the KUBECONFIG environment variable, so you must source it instead of just running it:
```
source ./finalize_setup.sh
```

### Test your cluster

```bash
kubectl get nodes
```