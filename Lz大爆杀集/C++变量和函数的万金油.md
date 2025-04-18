# Template模板&Auto变量
## 1.Template模板
`Template<typename T>`:声明了一个**模板参数**，表示"这里有一个类型T，具体是什么类型在使用时决定"。
```C++
template<typename T>  // 声明一个类型参数T
void myFunction(T param) {
    // 函数体可以使用T类型的param
}
```
假设你想写一个函数，可以处理int、double、string等多种类型：
### 没有模板的写法（需要重载多个函数）
```C++
void print(int value) { cout << value; }
void print(double value) { cout << value; }
void print(string value) { cout << value; }
// 每种类型都需要一个单独的函数
```
### 使用模板的写法（一个函数处理所有类型）
```C++
template<typename T>
void print(T value) {
    cout << value;
}
// 可以用于任何支持<<操作的类型
```
___
## 2.Auto变量
**基本用法**：自动类型推导

`auto`让编译器根据初始化表达式自动推导变量类型：
``` C++
auto i = 42;        // i是int类型
auto d = 3.14;      // d是double类型
auto s = "hello";   // s是const char*类型
auto v = {1, 2, 3}; // v是std::initializer_list<int>类型
```

### 主要应用场景

#### 1. 简化复杂类型声明

特别是对于迭代器和模板类型：
```C++
// 不使用auto
std::vector<std::pair<int, std::string>>::iterator it = vec.begin();
// 使用auto
auto it = vec.begin();  // 简洁明了
```
#### 2. 配合模板编程
```C++
template<typename T, typename U>
auto add(T t, U u) -> decltype(t + u) {
    return t + u;
}
```
### 2.3 范围for循环

cpp

复制

下载

std::vector<int> vec = {1, 2, 3};

// 不使用auto
for (std::vector<int>::iterator it = vec.begin(); it != vec.end(); ++it)

// 使用auto
for (auto it = vec.begin(); it != vec.end(); ++it)

// 更简洁的范围for
for (auto& element : vec) {
    element *= 2; // 可以修改元素
}
<!--stackedit_data:
eyJoaXN0b3J5IjpbNTQ3NzU4MjI1LDc5MTkyNTA0NF19
-->