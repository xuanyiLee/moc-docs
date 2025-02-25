# **REGEXP_SUBSTR()**

## **函数说明**

`REGEXP_SUBSTR()` 用于返回字符串 `expr` 中匹配正则表达式模式 `pat` 的子字符串。

## **语法**

```
> REGEXP_SUBSTR(expr, pat[, pos[, occurrence[, match_type]]])
```

### 参数释义

- `expr`：这是原始的字符串，在此字符串中查找匹配项。

- `pat`：这是正则表达式模式，函数会查找与此模式匹配的字符串。

- `pos`：这是一个可选参数，指定从哪个位置开始搜索。默认值是 1，表示从字符串的开始位置开始搜索。

- `occurrence`：这是一个可选参数，指定返回第几次匹配的字符串。默认值是 1，表示返回第一次匹配的字符串。如果此值为非零值 n，将返回第 n 次出现的匹配字符串。

- `match_type` 参数是一个可选的字符串，用于指定匹配的方式。这个参数可以由以下字符构成，每个字符指定一种匹配方式，字符的顺序不影响结果：

  - `'c'`：区分大小写进行匹配（即，大写和小写字母被视为不同的字符）。默认情况下，匹配区分大小写。
  - `'i'`：不区分大小写进行匹配（即，大写和小写字母被视为相同的字符）。
  - `'n'`：允许 `.` 符号匹配换行符。默认情况下，`.` 符号不会匹配换行符。
  - `'m'`：将字符串视为多行。即，`^` 匹配字符串的开头或任何行的开头，`$` 匹配字符串的结尾或任何行的结尾。默认情况下，`^` 只匹配字符串的开头，`$` 只匹配字符串的结尾。
  - `'u'`：将模式视为 UTF-8 字符串。默认情况下，模式视为字节字符串。

## **示例**

```SQL
mysql> SELECT REGEXP_SUBSTR('1a 2b 3c', '[0-9]a');
+---------------------------------+
| regexp_substr(1a 2b 3c, [0-9]a) |
+---------------------------------+
| 1a                              |
+---------------------------------+
1 row in set (0.00 sec)

mysql> SELECT REGEXP_SUBSTR('Lend for land', '^C') Result;
+--------+
| Result |
+--------+
| NULL   |
+--------+
1 row in set (0.00 sec)
```
