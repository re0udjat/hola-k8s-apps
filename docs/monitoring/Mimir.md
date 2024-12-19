# Mimir

## Install Grafana Mimir using Helm

**Step 1:** Create `mimir` namespace for managing and isolating resources of Grafana Mimir within a cluster:

```bash
kubectl create ns mimir
```

**Step 2:** Add and update Grafana Helm repository for the latest Mimir Helm chart:

```bash
helm repo add grafana https://grafana.github.io/helm-charts
helm repo update
```

**Step 3:** Install Grafana Mimir using the Helm chart:

```bash
kubectl config set-context --current --namespace mimir
kubectl install mimir grafana/mimir-distributed
```

**Step 4:** Verify that all Pods of Grafana Mimir is running normally:

```bash
kubectl get pods -n mimir
```
