# 🔄 Environment and Context Switching

> Controls switching of runtime environments, cloud accounts, and Kubernetes contexts. Global version switches (pyenv global, nvm use) and cloud account changes are denied to prevent accidental operations in the wrong environment.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
conda activate *
pyenv global *
nvm use *
rvm use *
rbenv global *
tfenv use *
kubectx *
kubectl config use-context *
kubectl config set-context *
aws configure *
gcloud config set project *
az account set *
direnv allow *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
pyenv local *
nvm alias *
direnv *
```

---
