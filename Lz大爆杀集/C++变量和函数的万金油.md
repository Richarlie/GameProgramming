# Template模板&Auto变量
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
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTgyMjg0MjgyXX0=
-->