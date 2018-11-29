Deploy a VM:

```
# Creating a virtual machine
$ kubectl apply -f https://raw.githubusercontent.com/kubevirt/demo/master/manifests/vm.yaml

# After deployment you can manage VMs using the usual verbs:
$ kubectl get vms
$ kubectl get vms -o yaml testvm

# To start a VM you can use
$ ./virtctl start testvm

# Afterwards you can inspect the instances
$ kubectl get vmis
$ kubectl get vmis -o yaml testvm

# To shut it down again
$ ./virtctl stop testvm

# To delete
$ kubectl delete vms testvm
```
