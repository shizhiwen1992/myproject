#### 一些基础
> python与C不同，不使用大括号而使用缩进来确定语句间关系，一般一缩进用四个空格。每句后不需要添加分号作为结尾。

---

#### 字符串
在python中，用引号括起来的都是字符串，引号可以是单引号也可以是双引号。

##### 1、合并（拼接）字符串
不同字符串之间可以使用“+”来合并。
```
first_name = 'ada'
last_name = 'lovelace'
print('full_name: ' + first_name + ' ' + last_name)
# 单引号内的字符串和已经定义好的字符型变量可以互相合并
```
输出结果：
```
full_name: ada lovelace
```
##### 2、用“方法”修改字符串
需要注意，使用“方法”修改字符串仅当次有效，**++++并没有改变原来的字符串变量的值++++**。如果想永久改变该变量需要将改变后的值赋给原变量。
##### .title()方法——首字母大写
对字符串变量使用.title()方法操作后，字符串中每个单词的首字母会变为大写。
```
name = 'ada lovelace'
print(name.title())
```
输出结果：
```
Ada Lovelace   #注意两个词的首字母均变为大写了
```

##### .upper()、.lower()方法——全部大（小）写
```
name = 'ada lovelace'
print(name.upper())
print(name.lower())
```
输出结果：
```
ADA LOVELACE   #全部大写
ada lovelace   #全部小写
```

##### .strip()方法——删除空白
对字符串变量用.rstrip()方法操作后，字符右侧（right）的空格被去掉。

.lstrip()——用于去掉左侧空格

.strip()——用于去掉两侧空格。

```
language = ' python ' 
print(language.strip()) 
print(language.lstrip())
print(language.rstrip())
```
输出结果：
```
python 
python 
 python
```
##### 3、关于单双引号
当字符内容中包含单引号时，内容需要使用双引号括起，同理内容包含双引号时，用单引号扩起，防止bug。


---

#### 数字
直接对数字进行计算，且不同类型的数字也可以混合进行计算。
但是数字和字符串不能合并。
```
age = 23
msg = 'Happy ' + age + 'rd birthday!'
print(msg)
```
如该程序就存在一处BUG，msg中的age是数值型数据，无法与前后的字符串合并。需要使用str()将数据类型转为字符串型后合并。
```
age = 23
msg = 'Happy ' + str(age) + 'rd birthday!'
print(msg)
```
输出结果：
```
Happy 23red birthday! 
```

---

#### 列表
列表由一系列按特定顺序排列而成的元素组成。

##### 列表的操作：
1、list定义
```
>>> li = ['a','b','shi','li','wang']
>>> li
['a','b','shi','li','wang']
>>> li[1]
'b'
```

2、list负数索引
```
>>> li = ['a','b','shi','li','wang']
>>> li[-1]
'wang'
>>> li[-3]
'shi'
>>> li[1:3]   # 顾头不顾尾,左闭右开区间
['b','shi']
>>> li[1:-1]
['b','shi','li']
```

3、list增加元素（三种方法）

.append()方法添加至末尾，区分.extend()方法，.extend()方法是将原对象与添加体合并，而.append是将添加体加入原对象中，具体可从将列表添加到列表时区分，.extend方法将新列表的元素加入原列表中，而.append将新列表整体作为一个元素加入原列表中（嵌套）。
```
>>> li = ['a','b','shi','li','wang']
>>> li.append('deng')
>>> li
['a','b','shi','li','wang','deng']
```

.insert()方法插入到指定位置
```
>>> li = ['a','b','shi','li','wang']
>>> li.insert('deng',2)
>>> li
['a','b','deng','shi','li','wang']
```

.extend()方法合并列表
```
>>> li = ['a','b','shi','li','wang']
>>> li.extend(['deng','lu'])
>>> li
['a','b','shi','li','wang','deng','lu']
# 如果是.append()结果将是：
>>> li
['a','b','shi','li','wang',['deng','lu']]
```

4、list搜索
```
>>> li = ['a','b','shi','li','wang','deng','lu']
>>> li.index('li')
3
>>> li.index('c')   #如果没找到值，会引发一个报错
Traceback (innermost last):
 File "<interactive input>", line 1, in ?
ValueError: list.index(x): x not in list
>>> 'C' in li
False
```

5、删除元素

.remove()方法移除
```
>>> li = ['a','b','shi','li','wang','deng','lu']
>>> li.remove('shi')
>>> li
['a','b','li','wang','deng','lu']
>>> li.remove('c')
Traceback (innermost last): 
 File "<interactive input>", line 1, in ? 
ValueError: list.remove(x): x not in list
```

.pop()方法弹出
```
>>> li = ['a','b','shi','li','wang','deng','lu']
>>> li.pop()  #.pop()会进行两个操作，移除列表末尾元素，并返回元素的值
'lu'
>>> li
['a','b','shi','li','wang','deng']
```

6、list运算
```
>>> li = ['a','b','shi']
>>> li += ['li','wang']
li = ['a','b','shi','li','wang']
