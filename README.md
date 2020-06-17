## Traefik on AKS


#### Install with Helm

```bash
# validate helm
helm repo add stable https://kubernetes-charts.storage.googleapis.com/
helm repo update
helm version

version.BuildInfo{Version:"v3.2.1", GitCommit:"fe51cd1e31e6a202cba7dead9552a6d418ded79a", GitTreeState:"clean", GoVersion:"go1.13.10"}

# install public chart with options
helm install traefik-ingress stable/traefik  --namespace kube-system --set dashboard.enabled=true,dashboard.serviceType=LoadBalancer,dashboard.domain=traefik.brianredmond.io,rbac.enabled=true
```

#### Test Ingress

```bash
kubectl apply -f test-example.yaml
```

#### Links

* Github. https://github.com/helm/charts/tree/master/stable/traefik 
* Docs. https://docs.traefik.io 

