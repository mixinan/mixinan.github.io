---
title: 正则表达式
date: 2018-10-20 15:43
---

一些正则表达式的练习题、答案。版权归属：达内科技。

<!-- more -->

<hr>

### 基本正则

^       以...开头，比如 ^#     (以 # 开头的行)
$       以...结尾，比如 hello$ (以 hello 结尾的行)
[ ]      从范围内选择一个字符，比如 [a-z]
[^a-z]  ^表示取反，小写字母范围之外的
.       任意单个字符

<hr>

\\{n\\}     符合前面条件的，出现 n 次，比如[a-z]\\{5\\}，连着 5 个小写字母  
\\{n,m\\}   符合前面条件的，出现 n~m 次  
\\{n,\\}    符合前面条件的，出现至少 n 次  
\*         匹配前一个字符 0 次或多次，比如 "ha*"    h  ha  haa   haaa 

			
## 扩展正则

{n}  出现 n 次  
\+   出现最少一次，比如"a+"  
?    出现最多一次（0 次或 1 次），比如"goo?"
|    或者，比如"^root|^abc"
\b   单词边界，比如 "\bvbc\b"，可以匹配到 vbc ，匹配不到hvbcdv
		
<hr>

[:space:] 空白字符  
[:punct:] 标点符号  
[:lower:] 小写字母  
[:upper:] 大写字母  
[:alpha:] 大小写字母  
[:digit:]  数字  
[:alnum:] 数字和大小写字母  

<hr>

grep -E  扩展正则，与 egrep 效果一样  
grep -n  显示行号  
grep -v  取反  
grep -i  忽略大小写  
grep -c  显示符合条件的个数  

<hr>

### 过滤文件中包含the 关键字的行

grep -n 'the' regular_express.txt

### 过滤文件中不包含the 关键字的行

grep -vn 'the' regular_express.txt

### 过滤文件中不论大小写 the 关键字的行

grep -in 'the' regular_express.txt

### 过滤 test 或taste 这两个单词

grep -n 't[ae]st' regular_express.txt

### 过滤有 oo 的行

grep -n 'oo' regular_express.txt

### 过滤 oo 前面不是 g 的行

grep -n '[^g]oo' regular_express.txt

### 过滤 oo 前面不想有小写字母的行

grep -n '[^[:lower:]]oo' regular_express.txt

### 过滤有数字的那一行

grep -n '[0-9]' regular_express.txt

### 过滤以 the 开头的

grep -n '^the' regular_express.txt

### 过滤以小写字母开头的

grep -n '^[[:lower:]]' regular_express.txt

grep -n '^[a-z]' regular_express.txt

### 过滤含有大写字母的

grep "[[:upper:]]" regular_express.txt

### 过滤两个大写字母相连的

egrep "[[:upper:]]{2}" regular_express.txt

### 过滤开头不是英文字母的

grep -n '^[^a-zA-Z]' regular_express.txt

### 过滤行尾结束为小数点.那一行

grep -n '\\.$' regular_express.txt

### 过滤空白行

grep -n '^$' regular_express.txt

### 过滤出 g??d 的字串

grep -n 'g..d' regular_express.txt

### 过滤至少两个o 以上的字串

grep -n 'ooo*' regular_express.txt

### 过滤 g 开头和 g 结尾但是两个 g 之间仅存在至少一个 o

grep -n 'goo*g' regular_express.txt

### 过滤任意数字的行

grep -n '[[:digit:]]' regular_express.txt

### 过滤两个o 的字串

egrep -n 'o{2}' regular_express.txt

### 过滤 g 后面接 2 到 5 个 o，然后在接一个g 的字串

egrep -n 'go{2,5}g' regular_express.txt

### 过滤 g 后面接 2 个以上o 的

egrep -n 'go{2,}g' regular_express.txt

   
### 过滤 oo 前面不是小写字母

grep -n '[^a-z]oo' regular_express.txt

### 过滤不是字母开头的

grep -n '^[^[:alpha:]]' regular_express.txt

### 过滤至少包含一位数的

grep -n '[0-9][0-9]*' regular_express.txt

<hr>


[下载练习文档](http://2hao.cc/download/regular.tar)