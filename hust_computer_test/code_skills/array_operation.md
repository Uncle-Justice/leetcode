# hust cs机试准备笔记——字符串


---

## 一、数组操作

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

5. 删除

    ```a.pop_back()```弹出最后一个元素

## 二、unordered_map、unordered_set的区别

- 哈希map是键值对，插入的时候需要同时给出key和value
- 哈希set是集合，**它的key和value是一体的**，所以插入的时候只用给一个元素
- 这两者当然在物理上都是使用哈希实现的，但是在代码层面，他们适用于不同的场景，不能完全等同

## 三、哈希集合操作

- **注意**：unordered_map、unordered_set的区别

1. 创建

```cpp
unordered_set<char> occ;
```

1. 插入/删除元素

```cpp
occ.insert(e);
occ.erase(e);
```

2. 检查某元素是否在集合中

不知道为什么这里是count，但是它的涵义就是在或不在，返回1或0

```cpp
occ.count(e);
```
