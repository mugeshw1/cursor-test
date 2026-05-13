# AI Agent Permission Policy

This file is the **index** of all permission rules for this project.
It is auto-loaded by all agents at session start.

> **MANDATORY**: Before executing any command, you MUST read the
> corresponding rules file for that category. Do NOT proceed without reading it.

---

## Rule Categories

| # | Category | Rules File | When to Read |
|---|----------|------------|--------------|
| 1 | Sensitive Files & Secrets | `rules/01-sensitive-files.md` | Before reading ANY file |
| 2 | Git Operations | `rules/02-git.md` | Before ANY git command |
| 3 | File System Operations | `rules/03-filesystem.md` | Before rm, mv, cp, chmod, etc. |
| 4 | Deployment & Publishing | `rules/04-deployment.md` | Before deploying or publishing |
| 5 | Database Operations | `rules/05-database.md` | Before ANY database command |
| 6 | Docker & Kubernetes | `rules/06-docker-k8s.md` | Before ANY docker/kubectl command |
| 7 | Cloud Providers | `rules/07-cloud.md` | Before ANY aws/gcloud/az command |
| 8 | System & Security | `rules/08-system-security.md` | Before system-level commands |
| 9 | Package Management | `rules/09-packages.md` | Before installing any package |
| 10 | Process Managers | `rules/10-process-managers.md` | Before pm2/celery/supervisor commands |
| 11 | Always Allowed | `rules/11-allowed.md` | Reference for safe commands |

---

## Quick Summary

### 🔴 Always Blocked (Never Execute)
- Reading secrets, keys, credentials, history files
- Force push, direct deploy to production
- Destructive DB operations (DROP, TRUNCATE, FLUSH)
- `rm -rf`, `kill -9`, `reboot`, `shutdown`
- Piping curl/wget directly into bash
- Privilege escalation (sudo su, passwd root)

### 🟡 Always Ask First
- Any `git push`, `git merge`, `git reset`
- Any `rm`, `mv`, package installs
- Any database client access
- Any cloud CLI command
- Any `sudo` usage

### 🟢 Always Allowed
- Read files (except denied ones)
- `git status`, `git log`, `git diff`, `git add`, `git commit`
- `ls`, `cat`, `echo`, `mkdir`, `touch`
- `npm run *`, `make`, `node`
- System info: `whoami`, `df`, `uptime`, `date`

---

## Notes

- **Deny > Ask > Allow** — deny rules always win conflicts
- **`disableBypassPermissionsMode`** is disabled — no permission bypass allowed
- When in doubt, **Ask** before executing
- Read the specific rules file for full details before acting
