# My Kubernetes Cheatsheet

## Create a pod in order to get a **interactive shell** inside the cluster

```
$ kubectl run shell --image nginx --generator=run-pod/v1
```
<details><summary>Output the command</summary>

```
pod/shell created
```
</details>

```
$ kubectl exec -ti shell -- /bin/bash
```
```
root@shell:/#
```

```
# apt-get -y update
# apt-get install -y curl
# apt-get install -y jq
# apt-get install -y dnsutils
```