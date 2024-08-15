# kubectl-grep

## Usage

```shell
kubectl grep NAME [TYPE]

DESCRIPTION
	Grep for specific patterns in Kubernetes object NAME and TYPE, and krep prints each lines that match the pattern.
	NAME is the Kubernetes object name PATTERN and TYPE is the Kubernetes object type PATTERN.

PATTERN
	Case insensitive pattern.
```

## Install

You just need to move the script named `kubectl-grep` in your `PATH`.

For example:

```shell
$ echo $PATH
/usr/local/bin:/usr/bin:/usr/local/sbin::/home/massi/.local/bin:/home/massi/.krew/bin:/home/massi/go/bin:/home/massi/.git-dclone
$ mv kubectl-grep ~/.local/bin/
```

And you're ready to go:

```shell
$ kubectl grep proxy                                                                                                                 [18:46:42]

configmaps
kube-system          kube-proxy                                             2      18m

pods
kube-system          kube-proxy-489hr                             1/1     Running   0          18m

serviceaccounts
kube-system          kube-proxy                                    0         18m

controllerrevisions.apps
kube-system   kube-proxy-79cf874c65   daemonset.apps/kube-proxy   1          18m

daemonsets.apps
kube-system   kube-proxy   1         1         1       1            1           kubernetes.io/os=linux   18m

events.events.k8s.io
kube-system          18m         Normal    Scheduled                 pod/kube-proxy-489hr                         Successfully assigned kube-system/kube-proxy-489hr to kind-control-plane
kube-system          18m         Normal    Pulled                    pod/kube-proxy-489hr                         Container image "registry.k8s.io/kube-proxy:v1.30.0" already present on machine
kube-system          18m         Normal    Created                   pod/kube-proxy-489hr                         Created container kube-proxy
kube-system          18m         Normal    Started                   pod/kube-proxy-489hr                         Started container kube-proxy
kube-system          18m         Normal    SuccessfulCreate          daemonset/kube-proxy                         Created pod: kube-proxy-489hr

rolebindings.rbac.authorization.k8s.io
kube-system   kube-proxy                                          Role/kube-proxy                                       18m

roles.rbac.authorization.k8s.io
kube-system   kube-proxy                                       2024-08-15T16:27:55Z
```
