# My Kubernetes Cheatsheet

## Create a pod in order to get a **interactive shell** inside the cluster

```text
$ kubectl run shell --image nginx --generator=run-pod/v1
pod/shell created
```

```text
$ kubectl exec -ti shell -- /bin/bash
root@shell:/#
```

```text
# apt-get -y update
# apt-get install -y curl
# apt-get install -y jq
# apt-get install -y dnsutils
```

## Get the IP addresses of the nodes

```text
$ kubectl get nodes -o json | jq '.items[].status.addresses[] | select(.type=="InternalIP") | .address'
"10.240.0.4"
"10.240.0.5"
"10.240.0.6"
```
