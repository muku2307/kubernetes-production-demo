# ☸ Kubernetes Production Concepts & Troubleshooting

> From "Why is my Pod Pending?" to "Why is my Ingress returning 503?"
>
> A hands-on reference of Kubernetes concepts, production patterns,
> failure scenarios, and troubleshooting techniques.

[Core Concepts] [Networking] [Health Checks] [Scaling] [Troubleshooting]

──────────────────────────────────────────────────────────────

## 🎯 What is this repository?

This isn't a Kubernetes tutorial.

It's a collection of practical scenarios and configurations
that demonstrate how Kubernetes behaves in real-world environments.

                    ┌─────────────────┐
                    │   Application   │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │    Ingress      │
                    └────────┬────────┘
                             │
                    ┌────────▼────────┐
                    │    Service      │
                    └────────┬────────┘
                             │
                 ┌───────────┴───────────┐
                 │                       │
           ┌─────▼─────┐          ┌─────▼─────┐
           │   Pod 1   │          │   Pod 2   │
           └───────────┘          └───────────┘


## 🧠 What you'll find here

| Area | What it covers |
|------|----------------|
| ⚙️ Workloads | Pods, Deployments, ReplicaSets |
| 🌐 Networking | Services, Ingress, DNS |
| 🔐 Configuration | ConfigMaps, Secrets |
| 📦 Resources | Requests, Limits, Quotas |
| ❤️ Health | Liveness, Readiness, Startup |
| 📈 Scaling | HPA, rolling updates |
| 🔍 Troubleshooting | Real-world failure scenarios |


## 🚨 Production Troubleshooting Lab

| Symptom | Possible Cause | Investigation |
|---------|----------------|---------------|
| `Pending` | Scheduling/resource issue | `describe pod` |
| `CrashLoopBackOff` | Container repeatedly exits | `logs --previous` |
| `OOMKilled` | Memory limit exceeded | Container state |
| `ImagePullBackOff` | Image/registry issue | Pod events |
| `NotReady` | Readiness probe failure | Probe/events |
| `503` | Backend unavailable | Service/Ingress |
<details>
<summary>🔍 CrashLoopBackOff — How would you investigate?</summary>

```bash
kubectl get pods
kubectl describe pod <pod>
kubectl logs <pod>
kubectl logs <pod> --previous

## 🗺️ Repository Roadmap

[✓] Core Kubernetes Concepts
[ ] Networking
[ ] Configuration
[ ] Resource Management
[ ] Health Checks
[ ] Scaling
[ ] Troubleshooting Lab

──────────────────────────────────────────────────────────────

Built as an independent technical reference.
No proprietary company code or configuration is included.
