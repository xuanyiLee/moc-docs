# **REGEXP_REPLACE()**

## **函数说明**

`REGEXP_REPLACE()` 用于将匹配给定正则表达式模式的字符串替换为指定的新字符串。

## **语法**

```
> REGEXP_REPLACE(expr, pat, repl[, pos[, occurrence[, match_type]]])
```

### 参数释义

- `expr` 是要替换的字符串。

- `pat` 这是正则表达式，函数会查找与此模式匹配的所有字符串。

- `repl` 是替换字符串，用于替换找到的匹配字符串。

- `pos`：这是一个可选参数，指定从哪个位置开始搜索。默认值是 1，表示从字符串的开始位置开始搜索。

- `occurrence`：这是一个可选参数，指定替换第几次匹配的位置。默认值是 1，表示返回第一次匹配的位置。

- `match_type` 参数是一个可选的字符串，用于指定匹配的方式。这个参数可以由以下字符构成，每个字符指定一种匹配方式，字符的顺序不影响结果：

  - `'c'`：区分大小写进行匹配（即，大写和小写字母被视为不同的字符）。默认情况下，匹配区分大小写。
  - `'i'`：不区分大小写进行匹配（即，大写和小写字母被视为相同的字符）。
  - `'n'`：允许 `.` 符号匹配换行符。默认情况下，`.` 符号不会匹配换行符。
  - `'m'`：将字符串视为多行。即，`^` 匹配字符串的开头或任何行的开头，`$` 匹配字符串的结尾或任何行的结尾。默认情况下，`^` 只匹配字符串的开头，`$` 只匹配字符串的结尾。
  - `'u'`：将模式视为 UTF-8 字符串。默认情况下，模式视为字节字符串。

## **示例**

```SQL
mysql> SELECT REGEXP_REPLACE('Hello, World!', 'World', 'Universe');
+------------------------------------------------+
| regexp_replace(Hello, World!, World, Universe) |
+------------------------------------------------+
| Hello, Universe!                               |
+------------------------------------------------+
1 row in set (0.00 sec)

mysql> SELECT REGEXP_REPLACE('Cat Dog Cat Dog Cat','Cat', 'Tiger') 'Result';
+---------------------------+
| Result                    |
+---------------------------+
| Tiger Dog Tiger Dog Tiger |
+---------------------------+
1 row in set (0.01 sec)
```
