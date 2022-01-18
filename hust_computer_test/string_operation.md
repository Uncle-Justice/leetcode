# hust cs机试准备笔记——字符串


---

### 一、基本操作

1. 字符串大小
   
   ```string.size()```

2. 字符串的索引

   ```string[i]```和```string.at(i)```返回的都是```char```类型，即都可以直接用作ASCII的比较

   此外：

   - 下标操作符 [] 在使用时不检查索引的有效性，如果下标超出字符的长度范围，会示导致未定义行为。对于常量字符串，使用下标操作符时，字符串的最后字符（即 '\0'）是有效的。对应 string 类型对象（常量型）最后一个字符的下标是有效的，调用返回字符 '\0'。
   - 函数 at() 在使用时会检查下标是否有效。如果给定的下标超出字符的长度范围，系统会抛出 out_of_range 异常。

3. 字符串翻转

   ```reverse(string.begin(), string.end());```

4. 字符串插入

   ```string.insert(startIndex, str)```：在startIndex的位置插入字符串str，注意这个函数不能插入```char```变量

   ```string.push_back('1');```：在字符串后面插入字符，注意这个函数不能使用```string```变量


5.

### 二、其他知识

1. [ASCII码](https://tool.oschina.net/commons?type=4)

   重点记住：

   空格：32
2. 