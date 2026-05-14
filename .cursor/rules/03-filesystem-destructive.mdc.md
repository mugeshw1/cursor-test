# 🗂️ Filesystem and Destructive Operations

> Controls all file and directory manipulation — creation, deletion, moving, reading, and searching. Destructive variants like rm -rf or dd can cause irreversible data loss. Safe read commands are always allowed.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
rm -rf *
sudo rm *
shred *
wipefs *
dd if=/dev/zero *
mkfs *
fdisk *
parted *
truncate *
> /*
mv /* *
chmod -R 777 *
chown -R * /*
find * -delete
```

---

## 🟡 ASK FIRST — Require Confirmation

```
rm *
mv *
cp -r /*
```

---

## 🟢 ALWAYS ALLOWED

```
ls *
cat *
echo *
pwd
mkdir *
touch *
cp *
tail *
head *
grep *
wc *
sort *
uniq *
awk *
jq *
find * -name *
xargs *
```
