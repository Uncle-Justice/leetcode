## 题目地址(0050.Pow(x, n))

https://leetcode-cn.com/problems/powx-n/

## 题目描述

## 关键词：分治法，递归

## 解法



1. 常规解法

但是因特殊情况超时而失败，比如n非常大，而且不仅n可能是负数，还要考虑x是复数的情况。。。复试应该不至于这么难

```cpp
class Solution {
public:
    double myPow(double x, int n) {
        if(n == 0){
            return 1.0;
        }
        if(x == 1.0)    return 1.0;
        if(n < INT_MIN) return 0.0;
        bool positive = n>0?true:false;
        n = positive?n:-n;
        double result = x;
        for(int  i = 1; i < n; i ++){
            result *= x;
            if(result > 100000)  break;
        }
        return positive?result:1/result;
    }
};
```

2. 分治法，递归（官

当我要算x^n的时候，我不需要算x^1, x^2, x^3, ... , X^n，实际上我只需要算X^1, x^2, x^4, ... , x^(n/2), x^n即可