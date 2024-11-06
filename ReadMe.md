helm-ys
=======

Support for using YAMLScript for Helm Templates


## Synopsis

```
$ helm install my-name . --post-renderer \
  $(curl -s https://yamlscript.org/helm-ys | bash)
Installed /tmp/helm-ys/bin/ys - version 0.1.82

NAME: my-name
LAST DEPLOYED: Wed Nov  6 14:25:35 2024
NAMESPACE: default
STATUS: deployed
REVISION: 1
NOTES:
1. Get the application URL by running these commands:
  export POD_NAME=$(kubectl get pods --namespace default -l "app.kubernetes.io/name=ys-test-chart,app.kubernetes.io/instance=my-name" -o jsonpath="{.items[0].metadata.name}")
  export CONTAINER_PORT=$(kubectl get pod --namespace default $POD_NAME -o jsonpath="{.spec.containers[0].ports[0].containerPort}")
  echo "Visit http://127.0.0.1:8080 to use your application"
  kubectl --namespace default port-forward $POD_NAME 8080:$CONTAINER_PORT
```
