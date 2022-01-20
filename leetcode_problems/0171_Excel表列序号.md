## 题目地址(171.Excel表列序号)

https://leetcode-cn.com/problems/excel-sheet-column-number/submissions/

## 题目描述

## 关键词：进制转换，字符串操作

## 解法

1. 常规方法（自己写的

```cpp
class Solution {
public:
    int titleToNumber(string columnTitle) {
        // 就是168的逆问题，更简单
        int result = 0;
        for(int i = 0; i < columnTitle.size(); i ++){
            result += pow(26, i) * (columnTitle[columnTitle.size() - i - 1] - 'A' + 1);
        }
        return result;
    }
};
```

