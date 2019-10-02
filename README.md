# Kubernetes monitoring prometheus and Grafana

## Requirement
- Volume atached to worker node with > 50Gi size.
- Mount volume to /data/volume2

## Run

`kubectl create -f prometheus/` 

This will create the following :
1. Namespace kube-monit, service account, cluster role and cluster role binding for prometheus.
2. Config map for prometheus config and end point.
3. Storage class, PV, and PVC for the prometheus server data directory.
4. Prometheus deployment and service with nodePort which can be access from http://master-ip:30010.

`kubectl create -f kube-state-metrics`

This will create the following :
1. Service account, cluster role and cluster role binding for kube state metrics.

### Deploy grafana

`kubectl create -f grafana/` 
