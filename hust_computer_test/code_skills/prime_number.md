# hust cs机试准备笔记


---

经初步分析，考试主要涉及的题目类型有：

**字符串的操作，数组的操作，基本的排序，进制转换，素数问题**

所以主要通过leetcode准备相关题型。

本目录主要记录与机试有关的一些知识点和题目链接

1. 基本概念

素数判定，注意只需要判断到根号就可以了，这样可以省很多的时间

```cpp
#include<cmath>
bool isPrime(int x){
    if(x < 2)
        return false;
    
    for(int i = 2; i <= sqrt(x); i++){
        if(x % i == 0)
            return false;
    }
    return true;
}
```