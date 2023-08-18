## bash小技巧
* 随机生成一段长度为n的字符串。
```
 echo $(uuidgen | tr -d '-')|cut -c1-16
```
