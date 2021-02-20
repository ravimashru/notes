# Restarting nginx controller

Required after updating TLS secrets with renewed certificate.

Get the name of the ingress controller pod in the `ingress` namespace:

```shell
$ kubectl get pods --namespace ingress
```

Start a shell in the pod:

```shell
$ kubectl exec -it <pod_name> -- /bin/sh
```

Execute in the pod:

```shell
$ nginx -s reload
```
