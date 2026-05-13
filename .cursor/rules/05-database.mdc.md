# Rules: Database Operations

> Read this before executing ANY database command.

---

## 🔴 DENIED — Never Execute

### Destructive Queries
```
psql * -c "DROP *"
psql * -c "DELETE *"
psql * -c "TRUNCATE *"
```

### Dump & Export
```
mysqldump *
pg_dump *
mongodump *
sqlite3 * .dump
```

### Cache Flush
```
redis-cli FLUSHALL
redis-cli FLUSHDB
redis-cli CONFIG *
```

### Other Destructive
```
influx delete *
clickhouse-client * --query "DROP *"
snowsql * -q "DROP *"
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

## 🟢 ALLOWED
None — all database access requires confirmation.
