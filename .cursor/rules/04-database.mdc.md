# 🗄️ Database Access and Data Export

> Governs all database client access and data export commands. DROP, TRUNCATE, FLUSH, and dump commands are denied outright. Interactive clients (psql, mysql, mongosh) require confirmation before connecting.

> **When to read this file:** Before executing any command in this category.

---

## 🔴 DENIED — Never Execute

```
psql * -c DROP *
psql * -c DELETE *
psql * -c TRUNCATE *
mysqldump *
pg_dump *
mongodump *
redis-cli FLUSHALL
redis-cli FLUSHDB
redis-cli CONFIG *
sqlite3 * .dump
influx delete *
clickhouse-client * --query DROP *
snowsql * -q DROP *
```

---

## 🟡 ASK FIRST — Require Confirmation

```
psql *
mysql *
mongosh *
redis-cli *
sqlite3 *
influx *
mongorestore *
psql * -f *
```

---
