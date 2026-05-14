# ⏰ Cron, Background Jobs, and Automation

> Governs scheduled task management — cron jobs, at/batch commands, and launchctl. Deleting all crontabs or loading system daemons is denied. Editing crontabs requires confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
crontab -r
crontab -l *
at *
batch *
launchctl load *
launchctl unload *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
crontab -e
crontab *
```

---

## 🟢 ALWAYS ALLOWED

```
crontab -l
```
