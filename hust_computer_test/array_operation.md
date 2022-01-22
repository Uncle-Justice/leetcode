# hust cs机试准备笔记——字符串


---

### 一、基本操作

1. 数组大小

    vector的大小```arr.size()```

2. 元素互换位置

    vector的元素互换位置```swap(arr[i], arr[j])```

3. 数组排序

    需要使用```#include <algorithm>```

    升序```sort(freq.begin(), freq.end());```
    
    降序```sort(freq.begin(), freq.end());
        reverse(freq.begin(), freq.end());```

4. 插入

    ```a.push_back(i)```注意这个下划线
    ```a.append(i)```