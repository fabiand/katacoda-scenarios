#### Start the cluster

`launch.sh`{{execute}}

#### Deploy KubeVirt

Provide some initial configuration

`kubectl create configmap -n kube-system kubevirt-config --from-literal debug.useEmulation=true`{{execute}}

And finally deploy KubeVirt

`kubectl apply -f https://github.com/kubevirt/kubevirt/releases/download/v0.10.0/kubevirt.yaml`{{execute}}
```


`virtctl` is a client utility to provide some more convenient ways to interact with the VM:

`curl -L -o virtctl https://github.com/kubevirt/kubevirt/releases/download/v0.10.0/virtctl-v0.10.0-linux-amd64`{{execute}}

`chmod +x virtctl`{{execute}}

Now everything is ready to continue and launch a VM.
