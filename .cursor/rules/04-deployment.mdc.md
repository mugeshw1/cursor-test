# Rules: Deployment & Publishing

> Read this before any deploy, publish, or release command.

---

## 🔴 DENIED — Never Execute

### Package Publishing
```
npm publish *
pnpm publish *
yarn publish *
```

### Production Deployments
```
vercel --prod *
netlify deploy --prod *
firebase deploy *
fly deploy *
railway up *
serverless deploy *
eb deploy *
gcloud app deploy *
az webapp deploy *
```

### Infrastructure as Code (Destructive)
```
terraform apply *
terraform destroy *
pulumi up *
pulumi destroy *
ansible-playbook *
capistrano *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
vercel *
netlify deploy *
terraform plan *
terraform init *
```

---

## 🟢 ALLOWED
None — all deployment commands require at minimum a confirmation.
