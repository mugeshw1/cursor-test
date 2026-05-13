# Rules: Docker & Kubernetes

> Read this before ANY docker, kubectl, or helm command.

---

## 🔴 DENIED — Never Execute

### Docker Destructive
```
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
```

### Kubernetes Destructive
```
kubectl apply *
kubectl delete *
kubectl rollout *
kubectl exec * -- rm *
kubectl exec * -- sh *
```

### Helm
```
helm install *
helm upgrade *
helm uninstall *
```

### Kubernetes Config & Context
```
kubectx *
kubectl config use-context *
kubectl config set-context *
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

## 🟢 ALLOWED
None — all Docker/Kubernetes commands require at minimum confirmation.
