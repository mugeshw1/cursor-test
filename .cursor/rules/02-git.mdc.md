# Rules: Git Operations

> Read this before executing ANY git command.

---

## 🔴 DENIED — Never Execute

### Force Push
```
git push --force *
git push -f *
```

### Protected Branch Checkouts
```
git checkout main
git checkout master
git checkout production
```

### History Rewriting
```
git filter-branch *
git filter-repo *
git rebase -i *
git commit --amend *
git reset --hard *
git clean -fd *
git clean -fX *
git reflog delete *
git gc --aggressive *
git update-ref -d *
git tag -d *
git push * --delete *
git push * --tags --force
git submodule deinit *
```

### Remote Manipulation
```
git remote add *
git remote set-url *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
git push *
git merge *
git rebase *
git reset *
git cherry-pick *
git bisect *
git tag *
```

---

## 🟢 ALLOWED — Safe to Execute

```
git status
git log *
git diff *
git add *
git commit *
git checkout -b *
git branch *
git stash *
git fetch *
git show *
```
