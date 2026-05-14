# 🏗️ Generated Files and Build Artifacts

> Prevents reading generated build directories and dependency caches (node_modules, dist, .next, __pycache__, vendor). These directories are noise for the agent and can contain sensitive cached data.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
**/node_modules/**
**/.git/**
**/dist/**
**/.next/**
**/.cache/**
**/build/**
**/.turbo/**
**/.vercel/**
**/.netlify/**
**/__pycache__/**
**/*.pyc
**/.gradle/**
**/.m2/**
**/target/**
**/.cargo/registry/**
**/vendor/**
```

---
