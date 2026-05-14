# ⚙️ System Configuration

> Governs low-level system settings — kernel parameters, firewall rules, bootloader config, hostname, timezone, and SELinux/AppArmor. These affect the entire machine. Safe system info commands are always allowed.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
sysctl -w *
systemctl disable *
systemctl mask *
systemctl stop *
update-rc.d *
chkconfig *
timedatectl set-timezone *
hostnamectl set-hostname *
ufw disable *
iptables -F
iptables --flush
nft flush *
setenforce 0
apparmor_parser -R *
grub-mkconfig *
update-grub *
systemctl enable *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
systemctl restart *
systemctl start *
systemctl reload *
ufw allow *
ufw deny *
```

---

## 🟢 ALWAYS ALLOWED

```
which *
whoami
id
uname *
df *
du *
free *
uptime
date
```
