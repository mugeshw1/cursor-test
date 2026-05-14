# ☁️ Cloud and Infrastructure

> Covers AWS, GCP, Azure, DigitalOcean, and Terraform. Destructive cloud operations (terminate instances, delete projects, create IAM keys) are denied. All other cloud CLI commands require confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
aws s3 rm *
aws s3 rb *
aws ec2 terminate-instances *
aws iam create-user *
aws iam attach-user-policy *
aws iam create-access-key *
gcloud projects delete *
gcloud compute instances delete *
gcloud iam service-accounts create *
az group delete *
az vm delete *
az ad sp create *
doctl compute droplet delete *
linode-cli linodes delete *
terraform import *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
aws *
gcloud *
az *
doctl *
terraform plan *
terraform init *
```

---
