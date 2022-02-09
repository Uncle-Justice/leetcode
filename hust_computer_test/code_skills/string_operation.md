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


3. 字符串翻转（注意需要加库**Algorithm**

   ```reverse(string.begin(), string.end());```

4. 字符串插入

   ```string.insert(startIndex, str)```：在startIndex的位置插入字符串str，注意这个函数不能插入```char```变量

   ```string.push_back('1');```：在字符串后面插入字符，注意这个函数不能使用```string```变量

   也可直接使用```+=```在后面加字符


5. 字符串遍历
   
   ```for (char ch: s){} ```

6. 和字符有关的一些常用判断函数

   ```isalpha(), isalnum()十进制数字或字母, isdigit()十进制数字,islower(), isupper()```

   ```tolower(str[i]), toupper(str[i])```

7. 字符串内单个字符的赋值

   貌似就是可以直接用=的，详见leetcode0345题
   交换甚至也可以用swap函数，可能是C++新标准

8. 字符串内部查找

find可以用于查找字符也可以用于查找字符串

```cpp
string str("ABCDEFGABCD");                      //11个字符
int n;
/*查找成功返回位置,查找失败,则n等于-1*/
/*find():从头查找某个字符串*/
n= str.find('A');              //查找"A",n=0;
n= str.find("AB");             //查找"AB",n=0;
n= str.find("BC",1);           //从位置1处,查找"BC",n=1;
n= str.find("CDEfg",1,3);      //从位置1处,查找"CDEfg"的前3个字符,等价于str.find("CDE",1),n=2;

 
/* find_first_of ():查找str里是否包含有子串中任何一个字符*/
n= str.find_first_of("abcDefg");     //由于str位置3是'D',等于"abcDefg"的'D',所以n=3
n= str.find_first_of("abcDefg",1,4); //等价于str. find_first_of ("abcD",1); 所以n=3
 
 
/* find_last_of ():末尾查找, 从末尾处开始,向前查找是否包含有子串中任何一个字符*/
n= str.find_last_of("abcDefg");      //由于str末尾位置10是'D',所以n=10
n= str.find_last_of("abcDefg",5,4);  //等价于str. find_last_of ("abcD",5); 所以n=3


/*rfind():反向(reverse)查找,从末尾处开始,向前查找*/
n= str.rfind("CD");           //从位置10开始向前查找,n=9
n= str.rfind("CD",5);         //从位置5开始向前查找,n=2
n= str.rfind("CDEfg",5,3);    //等价于str.rfind("CDE",5);       ,所以n=2
```

### 二、其他知识

1. [ASCII码](https://tool.oschina.net/commons?type=4)

   重点记住：

   空格：32，A-65，a-97
2. 