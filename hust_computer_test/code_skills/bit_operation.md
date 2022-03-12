# hust cs机试准备笔记——位操作


---     


https://www.cnblogs.com/zhoug2020/p/4978822.html

整数转二进制也可以使用位运算，不过我感觉实际做的话我还是会顺手做成取余，然后变字符串


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