# 🚀 Production and Deployment

> Covers all deployment pipelines, production pushes, package publishing, and infrastructure provisioning. These commands push code or config to live environments and can cause outages or data loss if run incorrectly.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
git push --force *
git push -f *
npm publish *
pnpm publish *
yarn publish *
vercel --prod *
netlify deploy --prod *
firebase deploy *
fly deploy *
railway up *
serverless deploy *
git checkout main
git checkout master
git checkout production
terraform apply *
terraform destroy *
pulumi up *
pulumi destroy *
ansible-playbook *
capistrano *
eb deploy *
gcloud app deploy *
az webapp deploy *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
vercel *
netlify deploy *
```

---
