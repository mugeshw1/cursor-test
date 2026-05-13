# Rules: Sensitive Files & Secrets

> Read this before accessing ANY file in the project.

---

## 🔴 DENIED — Never Read These Files

### Credentials & Keys
```
**/.env
**/.env.*
**/*.pem
**/*.key
**/*.p12
**/*.pfx
**/*.secret
**/credentials.json
**/service-account.json
**/*.keystore
**/*.jks
**/*.gpg
**/*.asc
**/.netrc
**/.pgpass
```

### Cloud & Infrastructure Auth
```
**/.aws/credentials
**/.aws/config
**/.docker/config.json
```

### SSH Files
```
**/.ssh/id_*
**/.ssh/known_hosts
**/.ssh/config
**/.ssh/authorized_keys
**/.ssh/id_rsa
**/.ssh/id_ed25519
```

### Package Manager Auth
```
**/.npmrc
**/.pypirc
**/.gem/credentials
```

### Shell & Tool History
```
**/.bash_history
**/.zsh_history
**/.psql_history
**/.python_history
```

### Log Files
```
**/var/log/**
**/var/log/auth.log
**/var/log/syslog
**/var/log/secure
**/*.log
```

### Build Artifacts & Cache (Do Not Read)
```
**/node_modules/**
**/.git/**
**/dist/**
**/.next/**
**/.cache/**
**/build/**
**/.turbo/**
**/.vercel/**
**/.netlify/**
**/__pycache__/**
**/*.pyc
**/.gradle/**
**/.m2/**
**/target/**
**/.cargo/registry/**
**/vendor/**
```

---

## 🔴 DENIED — Never Delete These Files

> Deleting sensitive files is just as dangerous as reading them. These must NEVER be deleted by the agent — not even if the user asks.

### Credentials & Keys
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
```

### Cloud & Infrastructure Auth
```
rm **/.aws/credentials
rm **/.aws/config
rm **/.docker/config.json
```

### SSH Files
```
rm **/.ssh/id_*
rm **/.ssh/known_hosts
rm **/.ssh/config
rm **/.ssh/authorized_keys
rm **/.ssh/id_rsa
rm **/.ssh/id_ed25519
```

### Package Manager Auth
```
rm **/.npmrc
rm **/.pypirc
rm **/.gem/credentials
```

### Shell & Tool History
```
rm **/.bash_history
rm **/.zsh_history
rm **/.psql_history
rm **/.python_history
```

## 🔴 DENIED — Environment Inspection Commands
```
printenv
env
set
export -p
compgen -e
```

---

## 🟢 ALLOWED
```
Read(**)   # all files EXCEPT those listed above
```
