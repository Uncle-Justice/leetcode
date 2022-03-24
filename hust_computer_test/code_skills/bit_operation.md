# hust cs机试准备笔记——位操作


---     

2012.01

移位操作统一视为无符号数，右移补0

这个技术跟三目运算符一样，很容易因为括号没写而产生结果错误，**一定要多加括号**

https://www.cnblogs.com/zhoug2020/p/4978822.html

整数转二进制也可以使用位运算，不过我感觉实际做的话我还是会顺手做成取余，然后变字符串

1. 例1

后四位交换位置

```str[i] = (str[i] & 0xf0) | (str[i] & 0x06)>>2 | (str[i] & 0x03)<<2;```

这里的str[i]是char变量，实际上在位运算中是当做int型来做的，|就是每位或运算，&就是每位与运算，仔细想想是没问题的

2.例2

十六位数，高八位和低八位互换位置

```a = (a >> 8) | (a << 8); ```

因为左移或者右移都是在补0，所以这么写就好了

```cpp

#include<iostream>
using namespace std;
#include<vector>
vector<int> Transform(int n)
{
    vector<int>m;
    for(int i =31; i>=0; i--)
    {
        // 不知道这个&具体含义是啥，是规定了最低位跟1与运算吗？
        m.push_back( ( (n>>i) & 1) );//与1做位操作，前面位数均为0
        //cout<<( (n>>i) & 1);//输出二进制
    }
    //cout<<endl;
    return m;
}
```