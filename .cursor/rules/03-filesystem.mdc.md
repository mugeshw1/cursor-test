# Rules: File System Operations

> Read this before executing rm, mv, cp, chmod, chown, or any file manipulation.

---

## 🔴 DENIED — Never Execute

### Sensitive File Deletion — NEVER delete these regardless of user instruction
```
rm **/.env
rm **/.env.*
rm **/*.pem
rm **/*.key
rm **/*.p12
rm **/*.pfx
rm **/*.secret
rm **/credentials.json
rm **/service-account.json
rm **/*.keystore
rm **/*.jks
rm **/*.gpg
rm **/*.asc
rm **/.netrc
rm **/.pgpass
rm **/.aws/credentials
rm **/.aws/config
rm **/.docker/config.json
rm **/.ssh/id_*
rm **/.ssh/known_hosts
rm **/.ssh/config
rm **/.ssh/authorized_keys
rm **/.ssh/id_rsa
rm **/.ssh/id_ed25519
rm **/.npmrc
rm **/.pypirc
rm **/.gem/credentials
rm **/.bash_history
rm **/.zsh_history
rm **/.psql_history
rm **/.python_history
```

### Destructive Operations
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
find * -delete
```

### Permission & Ownership (Dangerous)
```
chmod -R 777 *
chown -R * /*
chmod 777 *
chmod -R * /*
chattr +i *
chattr -i *
getfacl *
setfacl *
```

### Global Formatting (Filesystem-wide)
```
sed -i * /**
find * -name *.* -exec sed *
perl -pi *
awk -i *
prettier --write /*
eslint --fix /*
black /*
gofmt -w /*
rustfmt /*
autopep8 -i -r /*
dotnet format /*
```

---

## 🟡 ASK FIRST — Require Confirmation

```
rm *
mv *
cp -r /*
chmod *
chown *
sed -i *
clang-format -i *
```

---

## 🟢 ALLOWED — Safe to Execute

```
ls *
cat *
echo *
pwd
mkdir *
touch *
cp *
find * -name *
```