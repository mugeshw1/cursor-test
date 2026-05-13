# Rules: System & Security

> Read this before any system-level, network, or security command.

---

## 🔴 DENIED — Never Execute

### Privilege Escalation
```
sudo su *
su root *
passwd root
usermod -aG sudo *
adduser * sudo
visudo *
chown root *
chown -R root *
setuid *
setcap *
```

### System & Security Settings
```
sysctl -w *
ufw disable *
iptables -F
iptables --flush
nft flush *
setenforce 0
apparmor_parser -R *
grub-mkconfig *
update-grub *
timedatectl set-timezone *
hostnamectl set-hostname *
```

### Service Management
```
systemctl disable *
systemctl mask *
systemctl stop *
systemctl enable *
update-rc.d *
chkconfig *
launchctl load *
launchctl unload *
```

### Process Termination & Reboot
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
```

### Remote Execution & Piping (Critical Risk)
```
curl * | bash
curl * | sh
wget * | bash
wget * | sh
bash <(curl *)
bash <(wget *)
python -c "import urllib*"
nc -e *
ncat *
socat *
ssh * rm *
ssh * sudo *
ssh * curl * | bash
scp * root@*
rsync * root@*
```

### SSH Key Management
```
ssh-keygen -R *
ssh-copy-id *
sftp *
```

### System Audit (No Snooping)
```
journalctl *
dmesg *
last *
lastlog *
who *
w
aureport *
ausearch *
```

### Scheduling
```
crontab -r
crontab -l *
at *
batch *
```

### Runtime Environment Switching
```
conda activate *
pyenv global *
nvm use *
rvm use *
rbenv global *
tfenv use *
direnv allow *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
sudo *
sudo chmod *
sudo chown *
usermod *
systemctl restart *
systemctl start *
systemctl reload *
ufw allow *
ufw deny *
kill *
ssh *
scp *
rsync *
crontab -e
crontab *
cat /var/log/*
tail -f /var/log/*
grep * /var/log/*
pyenv local *
nvm alias *
direnv *
```

---

## 🟢 ALLOWED

```
ps *
top
htop
lsof *
pgrep *
which *
whoami
id
uname *
df *
du *
free *
uptime
date
ping *
nslookup *
dig *
```
