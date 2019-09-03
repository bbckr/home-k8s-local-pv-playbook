# home-k8s-local-pv-playbook
Example ansible playbook for managing local volumes in a Kubernetes cluster.

This example is used against the Kuberentes cluster provisioned in the [bbckr/home-k8s-setup-1](https://github.com/bbckr/home-k8s-setup-1) repository.

References for local static volume provisioning:
- Kubernetes Blog: [Local Peristent Volumes Beta](https://kubernetes.io/blog/2018/04/13/local-persistent-volumes-beta/)
- GitHub: [kubernetes-sigs/sig-storage-local-static-provisioner](https://github.com/kubernetes-sigs/sig-storage-local-static-provisioner)

## Example Usage
Preparing a local volume on a node:
``` bash
export TARGET="" # name of node in host inventory config
export DISK="" # name of whole disk to mount as filesystem
ansible-playbook playbook.yml -i hosts  --extra-vars "target=$TARGET disk_name=$DISK"

# example
ansible-playbook playbook.yml -i hosts  --extra-vars "target=master disk_name=sdb"
```
