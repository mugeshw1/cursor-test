# 🌐 Network and Supply Chain

> Prevents remote code execution via piped downloads (curl|bash), custom package registries, and raw TCP tools (nc, socat). Safe network utilities like curl, wget, ping, and dig are allowed.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
curl * | bash
curl * | sh
wget * | bash
wget * | sh
bash <(curl *)
bash <(wget *)
python -c import urllib*
pip install --index-url *
pip install --extra-index-url *
npm install --registry *
nc -e *
ncat *
socat *
```

---

## 🟢 ALWAYS ALLOWED

```
curl *
wget *
ping *
nslookup *
dig *
```
