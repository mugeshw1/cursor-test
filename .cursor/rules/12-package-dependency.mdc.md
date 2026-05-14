# 📦 Package and Dependency Management

> Manages package installation across all ecosystems (npm, pip, gem, cargo, apt). Global installs and custom registries are denied to prevent supply chain attacks. Local installs require confirmation. Run scripts are always allowed.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
npm install -g *
pnpm install -g *
yarn global add *
pip install --user *
gem install *
cargo install *
go install *
apt-get install *
apt install *
yum install *
brew install *
snap install *
flatpak install *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
npm install *
pnpm install *
yarn add *
pip install *
cargo add *
npx *
```

---

## 🟢 ALWAYS ALLOWED

```
npm run *
pnpm run *
yarn run *
node *
npm run build *
pnpm run build *
yarn build *
make *
```
