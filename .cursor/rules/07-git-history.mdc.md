# 📜 Git History and Repository Integrity

> Protects repository integrity by blocking history rewriting, force pushes, remote manipulation, and tag deletion. Safe read and normal commit/branch/fetch operations are always allowed.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
git remote add *
git remote set-url *
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

## 🟢 ALWAYS ALLOWED

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
