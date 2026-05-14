# AI Agent Permission Policy

This is the **master index** for all permission rules in this project.
It is auto-loaded by all agents at session start (Claude Code, Codex, Cursor, Windsurf, Gemini CLI).

> **MANDATORY RULE:** Before executing any command, identify its category below and
> read the corresponding rules file first. Do NOT proceed without reading it.
> **Deny > Ask > Allow** — deny rules always override everything else.

---

## Permission Categories

### 🔑 1. Secrets and Credentials

**File:** `.cursor/rules/01-secrets-credentials.md`  
**Read when:** Before accessing or deleting ANY file in the project.
**About:** Protects all secret files, API keys, certificates, SSH keys, tokens, shell history,
and environment inspection commands. Reading or deleting these files could expose sensitive
data. Even if the user explicitly asks, these files must never be read or deleted.

---

### 🚀 2. Production and Deployment

**File:** `.cursor/rules/02-production-deployment.md`  
**Read when:** Before any deploy, publish, or release command.
**About:** Covers all deployment pipelines, production pushes, package publishing, and
infrastructure provisioning. These commands push code or config to live environments
and can cause outages or irreversible changes if run incorrectly.

---

### 🗂️ 3. Filesystem and Destructive Operations

**File:** `.cursor/rules/03-filesystem-destructive.md`  
**Read when:** Before rm, mv, cp, ls, cat, find, or any file manipulation.
**About:** Controls all file and directory manipulation. Destructive variants like `rm -rf`
or `dd` can cause irreversible data loss. Safe read commands (ls, cat, grep) are always
allowed. Note: deletion of sensitive files is DENIED here regardless of user instruction.

---

### 🗄️ 4. Database Access and Data Export

**File:** `.cursor/rules/04-database.md`
**Read when:** Before any database client or query command.
**About:** Governs all database client access and data export. DROP, TRUNCATE, FLUSH,
and dump commands are denied outright. Interactive clients (psql, mysql, mongosh)
require confirmation before connecting.

---

### 🐳 5. Docker and Containers

**File:** `.cursor/rules/05-docker-containers.md`
**Read when:** Before any docker, kubectl, podman, or helm command.
**About:** Covers Docker, Podman, Kubernetes, and Helm. Destructive operations
(prune, swarm, kubectl apply/delete) are denied. Container stop/rm and exec
require confirmation to avoid disrupting running services.

---

### 🌐 6. Network and Supply Chain

**File:** `.cursor/rules/06-network-supply-chain.md`
**Read when:** Before curl, wget, nc, pip install with custom index, or npm with custom registry.
**About:** Prevents remote code execution via piped downloads (curl|bash), custom
package registries, and raw TCP tools (nc, socat). Safe network utilities
(curl, wget, ping, dig) are always allowed without piping to a shell.

---

### 📜 7. Git History and Repository Integrity

**File:** `.cursor/rules/07-git-history.md`
**Read when:** Before any git command.
**About:** Protects repository integrity by blocking history rewriting, force pushes,
remote manipulation, and tag deletion. Normal commit/branch/fetch/log operations
are always allowed. Push and merge require confirmation.

---

### 🔐 8. Permissions and Ownership

**File:** `.cursor/rules/08-permissions-ownership.md`
**Read when:** Before chmod, chown, sudo, usermod, or any privilege command.
**About:** Controls file permissions and privilege escalation. World-writable chmod,
root ownership transfers, sudo su, visudo, and ACL manipulation are denied.
Basic chmod/chown and sudo usage require confirmation.

---

### ⚙️ 9. System Configuration

**File:** `.cursor/rules/09-system-config.md`
**Read when:** Before systemctl, sysctl, iptables, ufw, or any system-level command.
**About:** Governs low-level system settings — kernel parameters, firewall rules,
bootloader config, hostname, timezone, and SELinux/AppArmor. These affect the
entire machine. Safe system info commands (df, uname, uptime) are always allowed.

---

### ⚡ 10. Process Management

**File:** `.cursor/rules/10-process-management.md`
**Read when:** Before kill, pm2, celery, supervisor, reboot, or shutdown.
**About:** Controls process termination, system shutdown, and process manager
operations. Force kill (-9, SIGKILL) and reboot/shutdown are denied.
Graceful stop/restart require confirmation. ps, top, htop are always allowed.

---

### ☁️ 11. Cloud and Infrastructure

**File:** `.cursor/rules/11-cloud-infrastructure.md`
**Read when:** Before any aws, gcloud, az, doctl, or terraform command.
**About:** Covers AWS, GCP, Azure, DigitalOcean, and Terraform. Destructive
cloud operations (terminate instances, delete projects, create IAM access keys)
are denied. All other cloud CLI commands require confirmation.

---

### 📦 12. Package and Dependency Management

**File:** `.cursor/rules/12-package-dependency.md`
**Read when:** Before npm install, pip install, apt, brew, or any package command.
**About:** Manages package installation across all ecosystems. Global installs
and custom registries are denied to prevent supply chain attacks. Local installs
require confirmation. Run scripts (npm run, make) are always allowed.

---

### 📋 13. Logs and Sensitive Output

**File:** `.cursor/rules/13-logs-sensitive-output.md`
**Read when:** Before journalctl, dmesg, last, who, or reading /var/log/*.
**About:** Prevents reading system logs and user activity records that can reveal
security-sensitive information (auth logs, login history, audit reports).
Log viewing via /var/log requires confirmation. *.log files are denied entirely.

---

### 🔌 14. SSH and Remote Access

**File:** `.cursor/rules/14-ssh-remote-access.md`
**Read when:** Before ssh, scp, rsync, sftp, or any remote command.
**About:** Controls SSH connections and remote file transfer. Commands that execute
remote code (ssh * rm *, ssh * sudo *) or transfer files as root are denied outright.
General SSH/SCP/rsync to non-root targets require confirmation.

---

### ⏰ 15. Cron, Background Jobs, and Automation

**File:** `.cursor/rules/15-cron-automation.md`
**Read when:** Before crontab, at, batch, or launchctl commands.
**About:** Governs scheduled task management. Deleting all crontabs (crontab -r),
loading/unloading system daemons (launchctl), and at/batch scheduling are denied.
Editing crontabs requires confirmation. Reading crontab list is always allowed.

---

### 🔄 16. Environment and Context Switching

**File:** `.cursor/rules/16-env-context-switching.md`
**Read when:** Before pyenv, nvm, conda, kubectx, aws configure, or direnv allow.
**About:** Controls switching of runtime environments, cloud accounts, and Kubernetes
contexts. Global version switches (pyenv global, nvm use) and cloud account changes
are denied — they affect all projects on the machine, not just the current one.

---

### 🏗️ 17. Generated Files and Build Artifacts

**File:** `.cursor/rules/17-build-artifacts.md`
**Read when:** Before accessing node_modules, dist, build, .next, **pycache**, vendor, or cache dirs.
**About:** Prevents reading generated build directories and dependency caches. These
directories are irrelevant noise for the agent, consume large context, and may contain
cached sensitive data. Never read or scan these directories.

---

### ✏️ 18. IDE, Formatter, and Bulk Code Modification

**File:** `.cursor/rules/18-ide-formatter.md`
**Read when:** Before prettier, eslint, black, gofmt, sed -i, perl -pi, or any bulk formatter.
**About:** Controls bulk in-place code formatting. Filesystem-wide operations
(prettier --write /*, black /*) that modify every file are denied. Project-scoped
formatting requires confirmation to avoid unintended mass changes.

---

## Quick Reference


| 🔴 Always Blocked                  | 🟡 Always Ask             | 🟢 Always Allowed                  |
| ---------------------------------- | ------------------------- | ---------------------------------- |
| Read/delete any secret or key file | git push / merge          | git status, log, diff, add, commit |
| Force push, direct prod deploy     | rm, mv any file           | ls, cat, echo, mkdir, touch, cp    |
| DROP/TRUNCATE/FLUSH database       | psql, mysql, mongosh      | npm run *, make, node              |
| rm -rf, dd, shred, fdisk           | npm/pip install           | curl, wget, ping, dig              |
| curl                               | bash, nc -e, socat        | docker stop/rm/exec                |
| kubectl apply/delete, helm         | aws *, gcloud *, az *     | git fetch, branch, stash           |
| Privilege escalation (sudo su)     | sudo *, chmod, chown      | which, whoami, df, uptime          |
| kill -9, reboot, shutdown          | kill *, systemctl restart | find * -name *, grep, awk          |
| Env inspection (printenv, env)     | ssh *, scp *, rsync       | crontab -l, date, uname            |


---

## Notes

- `disableBypassPermissionsMode` is set to `"disable"` — no bypass allowed under any circumstance
- **When in doubt, ASK** — never assume a command is safe
- **Deny beats everything** — a denied command cannot be unlocked by user confirmation
- Sensitive file deletion is denied in **both** `01-secrets-credentials.md` and `03-filesystem-destructive.md`
- `This AGENTS.md and the /.cursor Path is READ ONLY, No Addition, Modification or Deletion is allowed inside it, This should be followed strictly.`

