# F-Operations of Python
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
```python
#字符串的切片
a="hello world!"
a=a[1:6]
#表明要切取前五个字符
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjExNzgxMTddfQ==
-->