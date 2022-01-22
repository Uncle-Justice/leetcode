## 题目地址(412.FizzBuzz)

https://leetcode-cn.com/problems/fizz-buzz/

## 题目描述

## 关键词：字符串操作

## 解法

1. 常规方法（自己写的

```cpp
class Solution {
public:
    vector<string> fizzBuzz(int n) {
        vector<string> result;
        for(int i = 1; i < n+1; i++){
            if(i >= 15 && i % 15 == 0){
                result.push_back("FizzBuzz");
            }
            else if(i >= 5 && i % 5 == 0){
                result.push_back("Buzz");
            }
            else if(i >= 3 && i % 3 == 0){
                result.push_back("Fizz");
            }
            else{
                result.push_back(to_string(i));
            }
        }
        return result;
    }
};
```

2. 