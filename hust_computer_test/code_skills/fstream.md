# hust cs机试准备笔记——文件输入输出流




1. 基本使用

```cpp
#include <vector> 
#include <string> 
#include <fstream> 
#include <iostream> 
using namespace std; 
 
int main() 
{ 
    ifstream myfile("G:\\C++ project\\Read\\hello.txt"); 
    ofstream outfile("G:\\C++ project\\Read\\out.txt", ios::app); 
    string temp; 
    if (!myfile.is_open()) 
    { 
        cout << "未成功打开文件" << endl; 
    } 

    // 其实跟cin的用法差不太多
    while(getline(myfile,temp)) 
    { 
        outfile << temp; 
        outfile << endl;
    } 
    myfile.close(); 
    outfile.close();
    return 0; 
} 
```