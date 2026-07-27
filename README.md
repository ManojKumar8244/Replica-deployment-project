# Deploying Scalable Applications using ReplicaSets and Deployments

## Problem Statement Overview
Running applications on standalone Kubernetes Pods introduces single-point-of-failure risks: if a Pod crashes, the application becomes unavailable, a single Pod cannot handle high user traffic, and updating application versions requires manual Pod replacement. The objective of this project is to use ReplicaSets and Deployments to achieve high availability, horizontal scaling, and zero-downtime rolling updates.

## Solution Approach
I deployed a web application using Kubernetes workload controllers:
* **ReplicaSets:** Configured a ReplicaSet to ensure a defined number of Pod replicas are always running in the cluster, providing self-healing when Pods fail.
* **Deployments:** Managed application lifecycles using Deployments to enable declarative updates, effortless scaling, and seamless rolling updates/rollbacks without application downtime.
* **Networking:** Exposed the application through a Kubernetes Service to route incoming user requests to healthy Pod replicas.

## Dependencies and Tools
* Kubernetes Cluster
* `kubectl` CLI tool
* Docker Application Container Image
* YAML Configuration Files (`replicaset.yaml`, `deployment.yaml`, `service.yaml`)

## Execution Steps
1. **Deploy ReplicaSet:**
   ```bash
   kubectl apply -f replicaset.yaml
   kubectl get pods
