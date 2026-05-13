# Rules: Package Management

> Read this before installing, publishing, or updating any package.

---

## 🔴 DENIED — Never Execute

### Global Installs
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

### Registry Overrides (Supply Chain Risk)
```
pip install --index-url *
pip install --extra-index-url *
npm install --registry *
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

## 🟢 ALLOWED — Safe to Execute

```
npm run *
pnpm run *
yarn run *
npm run build *
pnpm run build *
yarn build *
make *
node *
```
