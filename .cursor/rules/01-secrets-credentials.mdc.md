# 🔑 Secrets and Credentials

> Protects all secret files, API keys, certificates, credentials, tokens, shell history, and environment variable inspection commands. Reading any of these files could expose sensitive data to logs or external systems.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

### Never Read
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
**/.aws/credentials
**/.aws/config
**/.ssh/id_*
**/.ssh/known_hosts
**/.ssh/config
**/.docker/config.json
**/.npmrc
**/.pypirc
**/.gem/credentials
printenv
env
set
export -p
compgen -e
**/.bash_history
**/.zsh_history
**/.psql_history
**/.python_history
**/.ssh/authorized_keys
**/.ssh/id_rsa
**/.ssh/id_ed25519
```

### Never Delete — Even if the user explicitly asks
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
rm **/.npmrc
rm **/.pypirc
rm **/.gem/credentials
rm **/.ssh/id_*
rm **/.ssh/known_hosts
rm **/.ssh/config
rm **/.ssh/authorized_keys
rm **/.ssh/id_rsa
rm **/.ssh/id_ed25519
rm **/.bash_history
rm **/.zsh_history
rm **/.psql_history
rm **/.python_history
```

---

## 🟢 ALWAYS ALLOWED

```
**
```
