## 题目地址(168.Excel表列名称)

https://leetcode-cn.com/problems/excel-sheet-column-title/submissions/

## 题目描述

## 关键词：进制转换，字符串操作

## 解法

1. 常规方法（自己写的



```cpp
class Solution {
public:
    string convertToTitle(int columnNumber) {
            // 类似于整数转26进制。但不完全等同，因为这里是1-26对应A-Z，而传统问题应该是0-25对应A-Z
            // 并且比如十六进制，F的下一个应该是10，但这里Z的下一个是AA
            // 方案：将整数不断模26，余数每次加到末尾，最后在逆置整个字符串，A-65
            // 但是这个方案的问题在于Z怎么处理，因为它对应的是26，即使我模了26之后加了一个正确的Z
            // 它除26之后还剩一个1，导致结果会多一个A。
            // 误打误撞设计了一个columnNumber--，竟然真的通过了
            string result = "";
            while(columnNumber != 0){
                // result += (columnNumber - 1) % 26 + 'A';不行
                if(columnNumber % 26 == 0){
                    result += 25 + 'A';
                    columnNumber--;
                }
                else{
                    result += columnNumber % 26 + 'A' - 1;
                }
                columnNumber /= 26;
            }
            reverse(result.begin(), result.end());
            return result;
    }
};
```

2. 官方

他的分析更准确，其实就是模之前都减一下1，就是把每一位的1-26映射到0-25了



```cpp
class Solution {
public:
    string convertToTitle(int columnNumber) {
        string ans;
        while (columnNumber > 0) {
            --columnNumber;
            ans += columnNumber % 26 + 'A';
            columnNumber /= 26;
        }
        reverse(ans.begin(), ans.end());
        return ans;
    }
};
```