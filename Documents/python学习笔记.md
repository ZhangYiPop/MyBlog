# 基础知识

##关于注释

> “#“ 是注释
>“““或者'''引号用来多行注释 PS：多行注释还可以用来全部打印出来。<br>
> example = ''' ……'''  print（example）这样子就能将引号全部打印出来。<br/>
>在python中引号 ' ”是一样的

##输入(格式化输出）
<http://www.cnblogs.com/vamei/archive/2013/03/12/2954938.html/>

```
name = input('name :')
age = int(input('age :'))
job = input('job :')

info = '''
--------NO.1 Info {_name}-----------
you just have 3 chance
 
Name : {_name}
Age :  {_age}
Job : {_job}

'''.format(_name = name,
     _age = age,
     _job = job)

print(info)

info = '''
--------NO.2 Info %s ------------
you just have 3 chance

Name : %s
Age : %d
Job : %s
``
''' % (name, name, age, job)

print(info)

info = '''
--------NO.3 Info {0} ------------
you just have 3 chance

Name : {1}
Age : {2}
Job : {3}
''' .format(name, name, age, job)

print(info)

```

```
# s是字符格式，d是正型格式
print('%d'%(productList.index(iter)),iter)

```

>print(typr(name))   打印变量类型 <br>
>


```
**\n**
回车

**\r**
回车且回到下行的最初始位置

**\t**
表示Tab
```

##列表，字典格式化输出（看着整齐）
> 1. import jason
> 按照json的样式输出

```
import json
json_list = json.dumps(buyList,indent = 1)
print('shopping list \n %s'%json_list)
```
## Print   输出带颜色
>开头 \033[31;1m
>结尾 \033[0m
 
```
print("added \033[31;1m%s\033[0m into shopping cart,your current balance id %s"%(buyList,salary))
```
##输入暗文
```
import getpass
password = getpass.getpass("password")
```


##if else
```
age_of_oldboy = 56

guss_age = int(input('guedd age :')）

if guss_age == age_of_oldboy :
    print('yes, you got it')
elif guss_age > age_of_oldboy :
    print('think it bigger')
elif guss_age < age_of_oldboy   :
    print('think it smaller')

```
###为什么要有强制锁进
>有强制锁进就省略了结束符 {} ；同级的代码不用缩进，子集代码要缩进。
>

##while

```
age_of_oldboy = 56

count = 0

maxCount = 3
'''
you just have 3 chance
'''

while maxCount != 0 :

    guss_age = int(input('guedd age :'))

    if guss_age == age_of_oldboy :
        print('yes, you got it')
        break
    elif guss_age > age_of_oldboy :
        print('think it bigger')
    elif guss_age < age_of_oldboy   :
        print('think it smaller')

    maxCount -= 1
else:
    print('too mang times')


```
>while 有 else ！！！
>
>

##FOR循环

```
for i in range(10):
    print('loop:',i)
else:
    print('正常走完了')
ーーーーーーーーーーーーーーーーーーーーーーーーーーー
for i in range(0,10,2):# 从0开始步长为2（隔一个循环）
    print('loop:',i)
else:
    print('正常走完了')

# 循环三次询问一次


```
>for 有 else ！！！



##Python3中字符和字节要区分开来
```
print('zhang yi 007'.encode('utf-8'))
print('zhang yi/23/ew/wd'.decode('utf-8'))
```


#数组（列表）
```
names = ['zhang yi','mei li','haomei','duibuqiE','重复','重复']

# 切片（读取）

 #  取第2个到第4个元素
print(names[1:3])
 #  取第4个元素
print(names[3])
 #  取倒数第2个元素
print(names[-2])
 #  取倒数第3个至倒数第一个 从左往右数顾头不顾尾
print(names[-3:-1])
 #  取从倒数第三个往后
print(names[-3:])
 # 步长切片
print('range names frome 0 to final step 2',names[0:-1:2])

# 增
names.append('追加')

names.insert(1,'插入下标为1的地方')
# 替换
names[2] = '改了下标为2的地方'

# 查 
	# 返回下标
names.index('插入下标为1的地方')
	# 查询目标在数组中重复的次数
names.count("重复")

# 改
 	# 反转
print('反转之前',names)
names.reverse()
print('反转之后',names)
	# 排序
names.sort() # 按照ASCLL码来排序的
print('排序之后',names)
	# 合并
names2 = ['cen1','cen2']
names.extend(names2)
print('增加之后',names)
# 删除
names.remove("追加")
 # 删除第一个元素
del names[0]
 # pop  删除数组下标的元素 也是删除的一种 PS：在下标为空时 默认删除最后一个
names.pop(1)

 #清空
names.clear()
print('da ying names',names)
 
```

## 深浅copy
 
###浅copy
```
person = ['zhang yi',['saving',100]]
p1 = person[:]
p2 = person[:]

person[0] = 'xia yu he'		
person[1][0] = 'gai bian cun kuan'

print('p1: %@ /n p2: %@',p1,p2)
```

#元祖(只读列表)
>元祖和列表很像，但是没有 增／删／改 的功能，只有查（和切片查询的功能）
>
>一些配置文件可能需要
>

```
names = ('zhang yi','mei zi')
print(names.count('zhang yi'))
print(names.index('mei zi'))

```

# 字典

```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# by zhang yi

# 字典是无序的 没有下标

info = {
   'name1' : 'zhang yi',
   'name2' : 'wang yue',
   'name3' : 'xiang xin',
}

print(info)

# 改变值
info['name1'] = '改变'
# 增值
info['name4'] = '新增'
# 删值
del info['name2']
info.pop('name4')
# 随机删除
info.popitem()
##########################
info = {
   'name1' : 'zhang yi',
   'name2' : 'wang yue',
   'name3' : 'xiang xin',
}

# 查找
   #不确定查找 返回bool
print(info.get('name2'))
   #返回值 none（没有的情况下）
while info.get('name4'):
   print('进去了')
   #返回值 bool
print('name5' in info)

b = {
   'bName': 'bName',
   'name1': 'update name1',
}

# 更新 可加可替换
info.update(b)
print(info)
print(info.items())
# 将字典转成列表   
dict_item = info.items()
print(type(dict_item))

# 初始化
newDic = dict.fromkeys([1,2,3],'new')
print(newDic)

# PS在字典中改变第二层的数据后其他的第二层数据也会跟着变
newDicChange = dict.fromkeys([7,8,9],[1,{"numbe":"name"},444])
print('newDicChange:',newDicChange)
newDicChange[8][1]["name"] = 'changName'
print('NewDicChange'.center(20,'-'))
print(newDicChange)

# 循环字典
print('循环字典'.center(20,'-'))
for i in newDicChange:
   print(i,newDicChange[i])
   #非搞笑方法
print('循环字典第二种非高效'.center(20,'-'))
for k,v in newDicChange.items():
   print(k,v)
   
# 三级菜单

```

#字符基本操作


```
name = 'zhah \tnhg yi'

print(name.capitalize())   #首字母
print(name.count('a'))      #统计字符串 
print(name.center(20,'-')) #总共打印20个 字符出来，从中间开始，不足的以'-'来补齐

print(name.endswith('い')) #判断以什么结尾 返回 True 或者 False
print(name.expandtabs(tabsize = 30)) # \t 表示空格，输出30个空格
print(name.find('h'))  #查找字符串的索引值(最左边开始的第一个)
print(name[name.find('y'):name.find('i')+1]) # 取字符串 从索引为y的取到索引为i的字符串 PS 注意顾头不顾尾

formatter = 'my name is {kName},i am {kYear} old.'
print(formatter.format(kName = 'zhangyi',kYear='23')) #字符串的格式化输出
print(formatter.format_map({'kName':'zhangyi','kYear':'23'})) #字符串的格式化输出 以字典的方式
print(formatter.isalnum()) #返回True False 来判断是否只有字母数字
print(formatter.isalpha()) #返回Bool 判断是否只含有字母
print('1A'.isdecimal()) #返回Bool 判断是否含有十进制
print('1 A'.isidentifier()) #返回Bool 是不是一个合法的变量
print('aA'.islower()) # 返回Bool 是不是小写
print('sd2'.isnumeric()) #返回Bool 是否是有数字
print('sd2'.isdigit()) #返回Bool 是否是有数字
print('Yfcnsdfnc3'.istitle()) #判断是不是首字母大写后面，后面是纯数字和字母字母小写
print('')
```

#集合

> list_1 = [1,2,3,4,555,4,36]
> list_2 = set([1,2,3,4])
> list_3 = set([3,6,7,8])

```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# by zhang yi

## 集合是用来 表示列表之间的关系的 并且还可以将列表之间相同的元素去重

# 集合也是无序的
list_1 = [1,2,3,4,555,4,36]
list_1 = set(list_1)


print(list_1,type(list_1))
print('-'.center(20,'-'))
list_2 = set([2,5,0,66,22,8])
print(list_1,list_2)

# 取交集
print('-'.center(20,'-'))
print(list_1.intersection(list_2))

# 取并集
print('-'.center(20,'-'))
print(list_1.union(list_2))

# 差集 (除去相同)
print('-'.center(20,'-'))
print(list_1.difference(list_2))

# 判断是否为list_1子集
print('-'.center(20,'-'))
print(list_1.issubset(list_2))

# 判断是否为list_2父集
list_2 = set([1,2,3,4])
print('-'.center(20,'-'))   
print(list_1.issuperset(list_2))

# 对称差集 (除去两个都有的,然后并起来)
print('-'.center(20,'-'))
print(list_1.symmetric_difference(list_2))

# 判断连个集合之间是否没有交集 没有交集的情况下 True
list_3 = set([3,6,7,8])
print('-'.center(20,'-'))
print(list_2.isdisjoint(list_3))

# 符号
   # | 并集 
print('-'.center(20,'-'))
a = list_1 | list_3
print(a)

# & 交集
print('-'.center(20,'-'))
print(list_1 & list_3)

# - 差集
print('-'.center(20,'-'))
print(list_1 - list_3)

# ^ 对称差集
print('-'.center(20,'-'))
print(list_1 ^ list_3)
```
#文件操作1
```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# by Zhang Yi


print('-'.center(20,'-'))
# Open file 打开文件

fileOp = open('haha','r',encoding='utf-8') #'r' 读写模式
print('Open file \n',fileOp)

data = fileOp.read()
data2 = fileOp.read()
print('-'.center(20,'-'))
# data1 data2
print('data1 data2 : \n',data,data2)
# 文件读取的时候中间有"光标" 读完不重置就无法再读取

# 覆盖或者重建文件
w = open('haha2','w',encoding='utf-8') #'r' 读写模式
w.write('jfjfiejifew\n')
w.write('天才写的')
w.close()
print('-'.center(20,'-'))

# 写文件
print('写文件 : \n',open("haha2",'r',encoding='utf-8').read())

# 'a' = append 追加
m = open("haha2",'a',encoding='utf-8')
m.write('\nhahahefwef')
print('-'.center(20,'-'))
# tes1
# 11t
data4 = open('haha2','r',encoding='utf-8').read()
print('test : ',data4)


```
# 文件操作2

>open(‘文件名称’ ,’r’,encoding) ==**只能读文件**==
>open(‘文件名称’ , ’w’,encoding) ==**只能写文件，如果文件名重复，那么就会覆盖原来的文件**==
>open(‘文件名称’,’a’,encoding) ==**添加数据到文件**==

```
file = open(‘文件名称’,’r’,encoding)
date = file.read #将文件全部读取
data = file.readline # 读取一行数据
print(file.tell)  # 显示数据的句柄
file.seek(0) # 重置文件句柄到0（初始值）

file.flush ().  #以w的形式open一个文件，写完后用这个命令将文件从缓存保存在硬盘上（强制刷新）
```

# 进度条

```
import sys
sys.stdout.write(‘#’)


```

#转码
>encode  后，在decode的时候一定要和encode的编码相同，否则就报错。</br>
>都转到uinicode这个中转，然后再转其他码
>


```
#!/usr/bin/env python 
# -*- coding: utf-8 -*-
# by Zhang Yi

import sys

print('-'.center(20,'-'))
# sys.getdefaultencoding
print('sys.getdefaultencoding : ',sys.getdefaultencoding())

s = "你好"
# s_to_uinicode = s.encode('gbk')
s_to_utf_8 = s.encode('utf-8')
s_to_gbk = s.encode('gbk')

print('-'.center(20,'-'))
# To Utf-8
print('To Utf-8 : ',s_to_utf_8
      )
print('-'.center(20,'-'))
# To GBK
print('To GBK : ',s_to_gbk)

print('-'.center(20,'-'))
# GBK to UTF-8
s_FromeGBK_to_UTF = s_to_gbk.decode('gbk').encode('utf-8 ')
print('GBK to UTF-8 : ',s_FromeGBK_to_UTF)

print('-'.center(20,'-'))
# Decode s_to_gbk
print('Decode s_to_gbk : ',s_to_gbk.decode('gbk'))

'''
print('-'.center(20,'-'))
# 错误写法
print('错误写法 : ',s_to_gbk.decode('utf-8'))
'''
```


## 时间写法
```
time_format = '%Y-%m-%d %X'
time_current = time.strftime(time_format)

```
# 实参形参

> 在关键字参数和实际参混合的情况下 关键字参数 不能 写在 实参 前面

```
#!/usr/bin/env python 
# -*- coding: utf-8 -*-
# by Zhang Yi

import time
def logge():
    with open('log.txt','a') as f:
        time_format = '%Y-%m-%d %X'
        time_current = time.strftime(time_format)
        f.write('%s haha \n '%time_current)



test = logge()
test2 = logge()


def test(x,y):
    print(x)
    print(y)

# 在关键字参数和实际参混合的情况下 关键字参数 不能 写在 实参 前面

# test(x = 3,2) #错误写法
test(3,y = 2) #正确写法
test(x = 3,y = 2)



```
## 默认参数

>默认参数的情况下，在不输入实参的时候按照定义值来

```
# 默认参数的情况下，在不输入实参的时候按照定义值来
def test2(x,y = 2):
    print('-'.center(20,'-'))
    # 非默认参数

    print('默认参数 : ',x)
    print('-'.center(20,'-'))
    # 默认参数
    print('默认参数 : ',y)
        
    
test2(4)
```
## 参数组
>可以传任意参数<br/>
>预留接口的感觉<br/>
>规范是*args<br/>

```
# 参数组 一定要往后放 预留接口的感觉 （传入元祖）
def test3(*args):
    print('-'.center(20,'-'))
    # 参数组
    print('参数组 : ',args)

test3(1,2,3,4,5)
test3(*[1,2,3,4,5])

# 把n个关键字参数(健值对） 转换成字典的方式传入
def test4(**kwargs):
    print('-'.center(20,'-'))
    # 传入字典
    print('传入字典 : ',kwargs)
    print('-'.center(20,'-'))
    # 判断是否有某个键
    if 'name' in kwargs:
        print('判断是否有某个键 : ','有Name')
    else:
        print('没有 name')


test4( name = 'zhang yi',age = '18',sexual = 'man')

def test5(name,age = 19,*args,**kwar\
        gs):
    print('-'.center(20,'-'))
    # 混合
    print('name: ',name)
    print('age: ',age)
    print('args: ',args)
    print('kwargs: ',kwargs)

# 因为在定义的时候第一和第二都是位置形参，所以在负值的时候也要按照顺序来 PS 关键字不能写在位置参数前
test5('zhang yi','New 18','ffefer' ,sex = 'man',hobby = 'iPhone')
#错误写法1： test5('zhang yi',age = 'New 18','ffefer' ,sex = 'man',hobby = 'iPhone')
#错误写法2：因为第二个位置就是给age预留的位置，这样写只能导致参数被重复负值 系统报错。 test5('zhang yi','ffefer' ，age = 'New 18',,sex = 'man',hobby = 'iPhone')
```
### 字符串转字典
```
b =  字典类型的字符
eval(b)

b['key'] = value


```

#修饰器
##修饰器和OC中的类别区别
>虽然两者都是为了增加新的方法而不改变源代码的行为
>Python中的修饰器是针对某个方法的行为
>Oc中的类别是针对的类的行为
