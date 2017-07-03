# Consul Chart with fixed IP

## Test Consul issue

```shell
$ minikube start
$ helm install -f values_minikube.yaml .
$ kubectl exec consul-server-0-0 consul kv put test test
$ minikube stop && minikube start
# Wait until cluster leadership is acquired
$ kubectl exec consul-server-0-0 consul kv get test
Error! No key exists at: test
```
