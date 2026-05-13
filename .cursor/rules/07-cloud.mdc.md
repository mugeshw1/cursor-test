# Rules: Cloud Providers

> Read this before ANY aws, gcloud, az, or doctl command.

---

## 🔴 DENIED — Never Execute

### AWS Destructive
```
aws s3 rm *
aws s3 rb *
aws ec2 terminate-instances *
aws iam create-user *
aws iam attach-user-policy *
aws iam create-access-key *
aws configure *
```

### Google Cloud Destructive
```
gcloud projects delete *
gcloud compute instances delete *
gcloud iam service-accounts create *
gcloud config set project *
gcloud app deploy *
```

### Azure Destructive
```
az group delete *
az vm delete *
az ad sp create *
az account set *
az webapp deploy *
```

### Other Cloud
```
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
```

---

## 🟢 ALLOWED
None — all cloud CLI commands require confirmation.
