# 🔐 Permissions and Ownership

> Controls file permission and ownership changes. World-writable chmod, root ownership, privilege escalation (sudo su, visudo, usermod), and ACL manipulation are denied. Basic chmod/chown require confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
sudo su *
su root *
chmod 777 *
chmod -R * /*
chown root *
chown -R root *
setuid *
setcap *
visudo *
usermod -aG sudo *
adduser * sudo
passwd root
chattr +i *
chattr -i *
getfacl *
setfacl *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
chmod *
chown *
sudo *
sudo chmod *
sudo chown *
usermod *
```

---
