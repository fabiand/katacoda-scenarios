### Wait for the cluster to be ready

Before we can startm, we need to wait for the Kubernetes cluster to be ready

`launch.sh`{{execute}}

Now we are ready to continue.

#### Deploy KubeVirt

Provide some initial configuration

`kubectl create configmap -n kube-system kubevirt-config --from-literal debug.useEmulation=true`{{execute}}

And finally deploy KubeVirt

`kubectl apply -f https://github.com/kubevirt/kubevirt/releases/download/v0.10.0/kubevirt.yaml`{{execute}}

Now let's wait until the API server is ready:
`kubectl wait -n kube-system --for condition=ready pod -l kubevirt.io=virt-api`{{execute}}


`virtctl` is a client utility to provide some more convenient ways to interact with the VM:

`curl -L -o virtctl https://github.com/kubevirt/kubevirt/releases/download/v0.10.0/virtctl-v0.10.0-linux-amd64`{{execute}}

`chmod +x virtctl`{{execute}}

Now everything is ready to continue and launch a VM.
