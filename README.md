# lsc_lab6
Lab6 solution for Large Scale Computing course

# Setup

1. Run minikube cluster
```bash
minikube start
```

2. Add nfs through helm repo
```bash
helm repo add stable https://charts.helm.sh/stable
helm repo update
helm install nfs-server stable/nfs-server-provisioner -f values.yaml
```

3. Install the application
```bash
helm install web-server .
```

4. Forward port to see the web output
```bash
kubectl port-forward service/web-server-service 8080:80
```
