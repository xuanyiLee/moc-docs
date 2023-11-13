# **VERSION**

## **函数说明**

`VERSION()` 函数用于获取当前 MatrixOne Cloud 系统的版本信息。这个函数通常返回一个字符串，包含了数据库管理系统的版本号。如 8.0.30-MatrixOne-v1.0.0-rc1，表示 MatrixOne Cloud 数据库的版本号是 8.0.30-MatrixOne-v1.0.0-rc1, 它的定义是 MySQL 兼容版本号 (8.0.30) + MatrixOne + MatrixOne 内核版本 (v1.0.0-rc1)。

## **函数语法**

```
> VERSION()
```

## **示例**

```sql
mysql> select version();
+-----------------------------+
| version()                   |
+-----------------------------+
| 8.0.30-MatrixOne-v1.0.0-rc2 |
+-----------------------------+
1 row in set (0.00 sec)
```
