# ⚡ Process Management

> Controls process termination, system shutdown, and process manager operations (PM2, Celery, Supervisor). Force kill and reboot commands are denied. Graceful stop/restart require confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
kill -9 *
killall *
pkill *
kill -SIGKILL *
reboot *
shutdown *
halt *
init 0
init 6
poweroff *
pm2 delete *
pm2 kill *
pm2 flush *
supervisorctl stop all
celery purge *
celery control shutdown *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
kill *
pm2 restart *
pm2 stop *
supervisorctl restart *
pm2 start *
celery *
```

---

## 🟢 ALWAYS ALLOWED

```
ps *
top
htop
lsof *
pgrep *
```
