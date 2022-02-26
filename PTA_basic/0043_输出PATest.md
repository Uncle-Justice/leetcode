## 题目地址(0043.输出PATest)


## 关键词：
## 解法

1. 自己的解法

主要是switch/case语句的使用

```cpp
#include<iostream>
#include<iomanip>
#include<vector>
using namespace std;
const vector<char> PATestDICT = {'P','A','T','e','s','t'};
int main(){
//  结果中，除了PATest没有其他的字符了
//  先统计六个字母的频率，再生成一个字符串，
    string input, result;
    getline(cin, input);
    vector<int> PATestFreqVec(6, 0);
    int PATestTotalSize = 0;
    for(char ch: input){
        switch(ch){
            case('P'):
                PATestFreqVec[0]++;
                PATestTotalSize++;
                break;
            case('A'):
                PATestFreqVec[1]++;
                PATestTotalSize++;
                break;
            case('T'):
                PATestFreqVec[2]++;
                PATestTotalSize++;
                break;
            case('e'):
                PATestFreqVec[3]++;
                PATestTotalSize++;
                break;
            case('s'):
                PATestFreqVec[4]++;
                PATestTotalSize++;
                break;
            case('t'):
                PATestFreqVec[5]++;
                PATestTotalSize++;
                break;
        }
    }
    while(PATestTotalSize != (int)result.size()){
        for(int i = 0; i < 6; i++){
            if(PATestFreqVec[i]>0){
                result+=PATestDICT[i];
                PATestFreqVec[i]--;
            }
        }
    }
    cout<<result<<endl;
    return 0;
}
```