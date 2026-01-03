# F-Operations of Python
## 基础语句
输出:
长空格 -\t
不换行 -,end=""
```python
a=input()# 输入
a=input("Please Load in:")#输入时顺便提示
a=int(input("Please Load in:")#圈定输入的数据范围
```
```python
#强制类型转换
a=15
b=str(a)
c=float(b)
```
```python
#随机数:
import random
a=random.randint(1,100)#1到100以内的随机整数
b=random.uniform(1,100)#1到100以内的随机小数
c=random.random()#直接获得从0到1之间的小数
```
```python
#布尔运算
a=false
b= not a#and or not 与或非
```
```python
#条件语句:
a=int(input("load:"))
if a<0 or a>100:
	print("Not right")
elif a<60:
	print("failed")
elif a<80:
	print("well")
else:
	print("excellent")
```
## 循环
```python
#循环语句:
#while循环:
a=0
while a<100:
	while a<10:
		a+=1
		print(a)
		if a==5:
			continue
	print("e")
print("end")

#for循环:
for i in range(10):#表示从0到9
#例:a=range(5) → [0,5) oder [0,4]
	print(i)
#亦可作:

 arr=[1,3,5,7,8]
for i in arr:
	print(i)
	
string = "ABCDEFG"
for i in string:
	print(i)
	
#实际上只要for循环的这个范围是列表 字符串 元组 集合就都可以
#由于py不像C那样有大括号括住循环范围，所以要严格规整缩进
```
## 字符串
```python
#字符串操作
#切片
a="hello world!"
a=a[1:6]
#表示要切取前五个字符
a=[:6]
#表示要切取从开始到第五个字符
a=[6:]
#表示要窃切取从第五个字符到最后
a=[1:5:2]
#最后一个表示步长，2也就是一个隔一个取
a=[::-1]
#表示把整个字符串反过来
a=[-5:-1]
#表示要切取从倒数第五个字符到倒数第二个字符
#py的范围都是左开右闭的

#替换
a="hello world!"
a=a.replace("hello","morning")

#分割
#例：按空格分割
arr=a.split(" ")
# [hello,world!]
#那要把零散的列表用“-”拼合起来
string="-".join(arr)
# hello-world!

#大小写转换
a = "hello".capitalize() #首字母大写
a = "hello".title() #全体大写
a = "hello".lower() #字符串中大写转小写
a = "hello".upper() #字符串中小写转大写
```
## 列表
```python
#列表(里面内容不拘一格，可以为所欲为)
array = [
	[[1,2,3][4,5,6][7,8,9]]
	[[1,2,3][4,5,6][7,8,9]]
	[[1,2,3][4,5,6][7,8,9]]
]
for a in array:
	for b in a:
		for c in b:
			print(c) 

#表中查找元素
b=12
a=[1,False,"happy",b,[1,2,3]]
if 1 not in a:
	print("...")
	
#表尾增加元素
a.append("abc")
#表中插入元素
a.insert(1,'t')
#表中元素删除
a.pop(0)#下标
a.remove("happy")#指定
a.clear()#清空
#表中元素修改
a[0]=123
# 表的复制
b=a
b=a.copy()
#两者区别为a变b是否跟着变，前者会，后者不会

#排序
a=[4,1,2,3]
a.sort()
a=sorted(a)
#前者直接修改列表中的元素，后者返回一个新列表
```
## 元组 · 集合 · 字典
1. 元组 
与列表的区别是：元组中的元素无法修改，只能访问
```python
	a=(1,2,3)
```
2. 集合
**无序性** **不重复性**
```python
a={1,2,3,4}
```
3. 字典
```python
d={"name":"hello"，"age":"20"}
#所谓键值对：“name”——键 "hello"——值
#等效于C++中的map和unordered map容器

#获取所有键
d.keys() #['name','age']
#获取所有值
d.values() #['pig',20]
#获取所有东西
d.items() #[('name','pig'),('age',20)]
```

## 函数
```python
#例：判断数字是否为偶数
def isDouble(n):
	if n%2 == 0:
		return True
	else:
		return False
#对于外部变量的声明
def day():
	global DAY
	if DAY%2 == 0:
		print("...")
	else:
		print(".")
	Day += 1

#若不知传入的参数的数量，用*args，代表省略
def k(n,*args)
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE3OTY4NDIwNTRdfQ==
-->