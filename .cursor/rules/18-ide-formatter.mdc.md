# ✏️ IDE, Formatter, and Bulk Code Modification

> Controls bulk code formatting and in-place file modification tools. Filesystem-wide operations (prettier --write /*, black /*) are denied. Project-scoped formatting requires confirmation.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

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
prettier --write *
eslint --fix *
black *
gofmt -w *
autopep8 *
clang-format -i *
sed -i *
```

---
