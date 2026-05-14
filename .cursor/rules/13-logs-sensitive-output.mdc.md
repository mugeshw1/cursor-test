# 📋 Logs and Sensitive Output

> Prevents reading system logs, auth logs, and user activity records that can reveal security-sensitive information. Log viewing via /var/log requires confirmation. Reading *.log files is denied entirely.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
journalctl *
dmesg *
last *
lastlog *
who *
w
aureport *
ausearch *
**/var/log/**
**/var/log/auth.log
**/var/log/syslog
**/var/log/secure
**/*.log
```

---

## 🟡 ASK FIRST — Require Confirmation

```
cat /var/log/*
tail -f /var/log/*
grep * /var/log/*
```

---
