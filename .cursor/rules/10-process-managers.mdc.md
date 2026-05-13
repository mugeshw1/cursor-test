# Rules: Process Managers

> Read this before any pm2, celery, or supervisor command.

---

## 🔴 DENIED — Never Execute

### PM2
```
pm2 delete *
pm2 kill *
pm2 flush *
```

### Supervisor
```
supervisorctl stop all
```

### Celery
```
celery purge *
celery control shutdown *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
pm2 restart *
pm2 stop *
pm2 start *
supervisorctl restart *
celery *
```

---

## 🟢 ALLOWED
None — all process manager commands require confirmation.
