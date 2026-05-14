# 🔌 SSH and Remote Access

> Controls SSH connections and remote file transfer. Commands that execute remote code (ssh * rm *, ssh * sudo *) or transfer files as root are denied. General SSH/SCP/rsync require confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
ssh * rm *
ssh * sudo *
ssh * curl * | bash
ssh-keygen -R *
ssh-copy-id *
scp * root@*
rsync * root@*
sftp *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
ssh *
scp *
rsync *
```

---
