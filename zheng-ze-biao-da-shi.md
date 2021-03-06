正则表达式由两部分组成：元字符和文本字符。元字符是具有特殊含义的字符，例如?代表任意字符。文本字符就是普通的文本，例如字母和数字。

### 范围匹配：[]
字符和方括号内的任意一个字符匹配都可以。例如[name]匹配n、a、m、e都行。[jjk]在目标串中寻找j和k。

#####区间：-
在方括号内的字符可能有很多，如果字符的编码中连续的，可以使用区间符号"-"，例如
[A-Z]，匹配大写字母
[A-Za-z]，匹配字母
[0-9]，匹配数字
###### 排除: ^
^出现在方括号内表示排除。例如`[^0-9]`表示除数字以外的字符。

### 通配符: .
正则表达式中的通配符为‘.’，表示任意长度的任意字符。例如.er匹配以er结尾的任意字符。

### 数量限定：
##### 至少一个：+
9+匹配一个或者多个连着的9
##### 不止一个或者零个：*
9*:没有或连着大于一个9
##### 一个或零个: ？
9?:有一个或没有
##### 指定个数范围{个数列}
9{3,5}:3个或者5个9，9{3,}:至少3个

### 位置限定:

##### 开始: ^字符
^adc.表示以abc开始的字符串。

##### 结尾: 字符$
abc$:abc只出现在字符串的结尾。

### 匹配划分:()
括号用于划分子串，所有对包含在子串内字符的操作都是以子串为整体进行的。括号字符也罢正则表达式分成不同部分的操作符。

### 或选择符: |
满足|两侧任意一个即可，例如：com|cn|com.cn|net。表示是com、cn、com.cn、net任意一个即可。

### 转义字符: \
由于以上字符具有特殊含义，想要匹配以上字符本身就不要特殊标明，就是使用`\`字符，`\`后的一个字符不再具有特殊含义，而是文本字符本身。而且`\\`表示`\`字符。表示，第一个`\`将后面的`\`转义，不再具有转义的含义，而是`\`本身。

### 使用字符类

匹配字符类

复制代码

[:a;num:]    任意字母和数字（同 [a-zA-Z0-9]）
[:alpha:]     任意字符（同 [a-zA-Z]）
[:blank:]     空格和制表（同 [\\t]）
[:cntrl:]        ASCII控制字符（ASCII 0到31和127）
[:digit:]       任意数字（同[0-9]）
[:graph:]    与["print:] 相同，但不包括空格
[:lower:]      任意小写字线（同 [a-z]）
[:print:]        任意可打印字符
[:punct:]      既不在 [:alnum:] 又不在 [:cntrl:] 中的任意字符
[space:]       包括空格在内的任意空白字符（同 `[\\f\\n\\t\\r\\v]）`
[:upper:]     任意大小字母（同 [A-Z]）
[:xdigit:]      任意十六进制数字（同 [a-fA-F0-9]）


匹配多个实例

复制代码
```
元字符              说明
*                      0个或多个匹配
+                      1个或多个匹配（等于 {1, }）
?                      0个或1个匹配（等于 {0, 1}）
{n}                    指定数目的匹配
{n, }                  不少于指定数目的匹配
{n ,m}                匹配数目的范围（m不超过255）
```
