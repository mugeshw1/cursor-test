# 🐳 Docker and Containers

> Covers Docker, Podman, Kubernetes, and Helm. Destructive container and cluster operations (prune, swarm, kubectl apply/delete) are denied. Container inspection and stop/rm require confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
kubectl apply *
kubectl delete *
kubectl rollout *
helm install *
helm upgrade *
helm uninstall *
docker volume rm *
docker system prune *
docker volume prune *
docker network prune *
docker image prune *
docker swarm leave *
docker swarm init *
docker stack deploy *
docker stack rm *
podman system reset *
kubectl exec * -- rm *
kubectl exec * -- sh *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
docker rm *
docker rmi *
docker stop *
docker exec *
podman rm *
```

---
