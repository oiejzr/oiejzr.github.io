---
layout: post
title: ''
subtitle: ''
date: 2019-08-30
categories: 公告
cover: 'http://on2171g4d.bkt.clouddn.com/jekyll-theme-h2o-postcover.jpg'
tags: OI 基础数据结构 栈 队列 链表
---

## 1.1栈
### 1.1.1栈的性质
我们发现：盘子都是从顶端进、从顶端出，所以如果x比y晚进入这叠盘子，那么x一定在y之前离开。

这个性质可以表达为“后进先出”。它是栈的本质。

栈(stack) : `LIFO (Last in first out)` 表

出入栈的时间复杂度：$O(1)$
### 1.1.2用数组实现栈
```cpp
int a[100005],tot=0;

#define push(x) s[++tot]=x //进栈
#define pop tot-- //弹出 出栈
#define size tot //栈的大小
#define top s[tot] //栈的顶部值
```
### Q1.1.a【例题】括号匹配问题
给定一个字符串，这个字符串由()[]{}这六个字符构成。如果所有的括弧都可以匹配上，那么就说这个字符串合法，否则非法。下面给一些例子：

`[({})]`：合法。

`[([]){}[]]{}`：合法。

`{{}`：非法。

`([)(])`：非法。

我们的任务是写一个程序，判断给定字符串是否合法。
### Q1.1.a【例题】分析
我们用一个栈来维护当前所有没有匹配的括号.

当新加入一个括号的时候：

- 如果是左括号，则把这个括号入栈.
- 如果是右括号，则看栈顶是否能和这个右括号匹配，如果可以的话则弹栈，否则这个括号序列不能匹配.
### 1.1.3用STL实现栈
头文件：`#include<stack>`

定义：`stack <元素类型> s;`【结构体亦可】

入栈：`s.push(入栈的元素);`

判断空栈：`s.empty();`【如果栈空，empty()返回1】

读取栈顶元素：`s.top();`

出栈：`s.pop();`
### 1.1.4栈与结构体
eg.
```cpp
struct ttp {
	int a,b;
	char c;
};
stack <ttp> rxz;

a.rxz.push();
b.rxz.pop();
```
### 1.1.5表达式树
![n9ESfS.png](https://s2.ax1x.com/2019/09/01/n9ESfS.png)

## 1.2队列
### 1.2.1队列的性质
队列的本质是：越先来的，越早办完事离开。

队列(queue) : FIFO (First in first out) 表.
### 1.2.2用数组实现队列
```cpp
int s[100005],fnt,end; //fnt指向队首，end指向队尾
#define push(x) s[++end]=x
#define pop fnt++
#define front s[fnt]
#define size end-fnt+1
```
![n9EM6J.png](https://s2.ax1x.com/2019/09/01/n9EM6J.png)

### 1.2.3循环队列
![n9EUpD.png](https://s2.ax1x.com/2019/09/01/n9EUpD.png)

当end达到MAX时，s[i%n] (i>MAX)
	1.2.4用STL实现队列
头文件：`#include<queue>`

定义：`queue <元素类型> q;`【结构体亦可】

访问队首元素：`q.front();`

入队：`q.push(入队的元素);`

判断空队：`q.empty();`【如果队空，empty()返回1】

出队：`q.pop();`

队的元素数量：`q.size();`
### Q1.2.a【例题】约瑟夫问题
一群小朋友坐成一个圈，已经按照顺时针 1...n 编号。从 1 号小朋友开始报数，报到 k 的小朋友出局；下一个小朋友继续从 1 开始报。显然，游戏进行到最后，场上只会剩下一个小朋友。此时这个小朋友获胜。我们的问题是，给定n和k，问被淘汰的n-1个小朋友出局的顺序。
数据范围：n,k<=1000
### Q1.2.a【例题】分析
![n9Evu9.png](https://s2.ax1x.com/2019/09/01/n9Evu9.png)

将小朋友们记为一个队列，将处于队首的小朋友移到队尾，至第k+1次操作时枪毙处于队首的小朋友
算法时间复杂度：O(nk)

### 1.2.5双端队列
定义：`dueue <元素类型> q;`【结构体亦可】
```cpp
d.push_front();
d.push_back();
d.pop_front();
d.pop_back();
d.front() //队首元素
d.back() //队尾元素
d[i] //d的第i个元素（复杂度高达O(n)，不建议使用）
```
### 1.3链表
### Q1.3.a【例题】洛谷FMT
月黑风高夜，一大群人排成一排，围观洛谷大厦。
次日，每个人都只记得自己右手边站的是谁。

如何利用这些信息，恢复出昨晚的排队顺序？

e.g. 1-4    2-5    3-2   4-3    5-none 
### 1.3.1链表的性质
链表的本质：相邻元素相连接。

链表中的存储单元地址连续不连续均可

分类：
![n9Vi9O.png](https://s2.ax1x.com/2019/09/01/n9Vi9O.png)

### 1.3.2链表的操作
- 任意查询 (例如：查询某元素的后继是谁)
- 任意插入 (在任意指定位置插入元素)
    - 将a1的指针指向p
    - 将p的指针指向a3
- 连接两个单链表
    - 将a[end]的指针指向b[1]
## 1.4并查集
### 1.4.1并查集的定义
把一个集合的bin最终指向的那个元素，称为这个集合的代表。
>
>-Union	将两个（不相交的）集合合并
>
>Find	查询一个元素所在集合的代表（进而可以实现Ask）
>
如图，该集合的代表为1
![n9Z9qs.png](https://s2.ax1x.com/2019/09/01/n9Z9qs.png)
### 1.4.2路径压缩
在之前的并查集中，我们发现最坏情况时，如图1，

查询1需要从1一直遍历至5，时间复杂度达到O(n2)

因此，我们在每次ask时，将该节点bin指向代表

如图2.此时，并查集相当于图3

时间复杂度低至O(n α(n))≈O(n)
![n9ZDFP.png](https://s2.ax1x.com/2019/09/01/n9ZDFP.png)
实现如下：
```cpp
if(x == bin[x])
{
		return x;
}
bin[x] = anc(bin[x]);
return bin[x];
```

## 1.5哈希表 / Hash表
### Q1.5.a【例题】询问朋友
你有一些朋友，每个朋友都有一个身份证号(13位，全是数字)。需要支持两个操作：

①添加一个新朋友 

②给定身份证号，问这个人是不是你的朋友。

### 1.5.1 Hash初步
在缩小数据规模至6位号码的情况下，可以建立数组w[1000000]，如果有人的id为x则把w[x]记为1.查询的时候，直接去看w[x]即可。

恢复数据规模

。。。

我们还是开一个数组，大小为p.

Add操作：w[id%p]=1.

Ask操作：看w[id%p]是否为1.为1则认为是朋友。

### 1.5.2 Hash碰撞
此时发现问题，若p=233333

Add w[2]=1;

Ask w[233335]

此时发现w[233335]为1，不符。总结得出：

若hash(x)==hash(y)，将会产生冲突，导致回答失败。

假设id%p是完全随机的。那么我们有定理：期望每 个朋友中，有两个人的id%p会相等。

这种情况称为“hash碰撞”。

为了尽量减少碰撞，p应当取得尽量大。

### 1.5.3减小Hash碰撞的概率
①取两个模数p1,p2.当且仅当这两个模数同时认为此人是我们的朋友，我们才回答YES.

采用双模数（甚至三模数），会显著降低碰撞概率。
②这个p一般要取质数。给出一个很简单的例子：如果p取6，偶数模6只会有三种取值，那么w数组只有三位被利用；如果p取5，那么w数组的每一位都会被利用起来。

### 1.5.4解决hash碰撞的问题【拉链法】
容器`vector`的用法：
头文件：#include<vector>
定义：vector <变量类型> v;
```cpp
v.clear();			//清空容器 
v.erase(pos);		//删除位置为pos的元素 
v.erase(begin,end);	//删除区间[begin,end)的所有元素 
v[i];				//访问第i个元素，用法与数组相同 
v.front();			//返回第一个元素 
v.back();			//返回最后一个元素 
v.push_back(e);		//在尾部添加元素e 
v.pop_back();		//移除最后一个元素 
v.push_front(e);	//在头部添加元素e 
v.pop_front();		//移除第一个元素 
```
拉链法的原理：设ha=8

%后数的列举	Vector（查询vector中是否有指定元素）
![n9emff.png](https://s2.ax1x.com/2019/09/01/n9emff.png)
拉链法的实现：
```cpp
vector <int> w[ha + 5];
w[x%ha].push_back(); //+for读入
scanf(“%d”,&x); //+for读入
for(int i=w[x%ha].begin();i<w[x%ha].end;i++) //遍历hash内的vector
{
	if(*i==x) //查找vector内是否有ask数
	{
		puts(“Yes”);
		return 0;
	}
}
puts(“No”);
```

### 1.5.5用STL维护Hash表
头文件：	#include<unordered_set>
定义hash表：unordered_set <变量类型> S;
Add元素：S.insert(元素);
查找元素：S.count(元素);				【如果存在，返回1】



## 1.6堆
### 1.6.1堆的定义
①它是树形结构，每个节点拥有一个key

②父亲节点的key必大于两个儿子节点 //大根堆
![n9eDB9.png](https://s2.ax1x.com/2019/09/01/n9eDB9.png)

### 1.6.2堆的插入
核心思想：修复

  修复方法：
- 直接将它摆在堆的末尾
- 如果它的key值比父亲大，则交换它和父亲，递归执行。
- 直到它的key值比父亲小，修复完毕。
![n9eR1O.png](https://s2.ax1x.com/2019/09/01/n9eR1O.png)

### 1.6.3堆的删除
堆的删除仅限于删除根节点。

如何删掉一个根节点呢？

- 核心思想：修复
- 直接把它和末尾的元素交换，然后直接删掉它
- 现在，原先在末尾的元素到了根节点。
- 在子节点中选个较大的，与x交换。递归执行以修复堆。

### 1.6.4堆的存储
直接利用数组来存
```cpp
LE(x) = x*2 //x的左节点
RT(x) = x*2+1 //x的右节点
DAD(x)= x/2 //x的父亲
```

### 1.6.5堆的代码
```cpp
    int s[500005];
    int tot; //记录堆的末尾值
    
    int top() //返回堆的根节点
    {
        return s[1];
}

    void modify(int x) //在插入时维护堆的性质
    {
        if(x==1) return; //如果已经是根节点则直接返回
        if(s[x] > s[DAD(x)]) //如果儿子比父亲大
            swap(s[x],s[DAD(x)]),modify(DAD(x)); //儿子当爸爸，维护
}
    void push(int key) //在末尾插入一个元素
    {
        s[++tot]=key;
        modify(tot); //维护
    }
    void repair(int x)  //在删除时维护堆的性质
    {
        int tar=s[LE(x)]>s[RT(x)]?LE(x):RT(x); //tar为左右儿子中大的那个
        if(s[x]<s[tar]) //如果儿子比父亲大
            swap(s[x],s[tar]),repair(tar); //儿子当爸爸，维护
    }
    void pop() //删除
    {
        s[1]=s[tot]; 
        s[tot--]=0; //弹出根节点
        repair(1); //维护
}
```
### 1.6.6用STL写一个堆
`priority_queue <int>` 支持：
```cpp
top();
push();
pop();
size();
empty();
```
默认是大根堆。想改成小根堆，可以采用`greater <int>`.

支持结构体，需要定义结构体的小于号。
## 1.7简易分块
### Q1.7.a【引入】教务处的工作
假设您是哈工大教务处的人员，某系共有100个班。您经常被问这样的问题：

$[𝑙,𝑟]$这些班的总人数是多少？

面对这种询问，您只好去从l班开始，到r班结束，把所有班级的人数全都加起来。那么最坏情况下，您需要对100个数求和，人都要累死23333

有更好的方法吗？

### Q1.7.a【分析】
可以在小本本上记录下10个值：

$[1,10]$班的人数之和、$[11,20]$班的人数之和……

Q:利用这些预先计算好的信息，如何加速每次查询？

A:eg.$[12.98]=12+13+···+[20,30]+[30,40]+···+[80,90]+91+···+97+98$

Q:最坏情况下，现在每次查询需要对多少个数求和？
A:9+8+9=27次

Q:如果有10000个班级，块的大小应该如何调整？

A：若有n个班，分为$\sqrt(n)$块

Q：如果有学生退学了怎么办！

A：修改小本本上的值即可

### 1.7.1分块的性质
分块是将整个区间分成若干块，维护整块的信息，以加速查询。


分块是有n的分支的(线段树!)

分块维护区间和、积

分块维护区间max/min

分块策略：设块大小为𝑇，则𝑥在⌊𝑥/𝑇⌋这个块。
		 块为[·    )[·
### Q1.7.b【例题】区间众数
给定序列a，有1w次询问，每次询问区间[l,r]的众数。

要求复杂度比𝑂(𝑛^2)快就行。
### Q1.7.b【分析】

- 分块记录每块内的众数k[i]
- 开vector类型记录k[i]的出现位置
- 对于区间，二分查找vector中区间内的出现位置
并比较

时间复杂度：$O(m\sqrt n log n)$
## 1.8单调栈
### Q1.8.a Problem
今有一群小朋友站队，每个小朋友想知道离自己最近的比自己高的人是谁。若没有这种人，则输出-1.

要求𝑂(𝑛)求出所有人的答案。

样例：这群人身高分别为

`3 5 2 1 9 7 6 8`
### Q1.8.a分析
我们把问题拆成两个小问题：对于每个小朋友，需要知道
- 在她前面的，离她最近的比她高的人是谁
- 在她后面的，离她最近的比她高的人是谁
我们发现它们是同一种问题。这是因为：如果解决了第一个问题，那么把这群人翻转一下，立刻就能解决第二个问题。

假设小朋友们在排队，哪些小朋友被挡住了？

我们从前往后扫这个序列，拿一个栈维护当前的小朋友能看到的人。

对于每一个小朋友：
-把栈里面比她低的人全都弹出去
-目前的栈顶就是答案
-把这个小朋友加入栈

### 1.8.1单调栈的性质
使用单调栈可以找到元素向左遍历第一个比他小的元素，也可以找到元素向左遍历第一个比他大的元素。

顾名思义，单调栈就是栈内元素单调递增或者单调递减的栈，这一点和单调队列很相似，但是单调栈只能在栈顶操作。

单调栈有以下两个性质：
- 若是单调递增栈，则从栈顶到栈底的元素是严格递增的。若是单调递减栈，则从栈顶到栈底的元素是严格递减的。
- 越靠近栈顶的元素越后进栈。
单调栈与单调队列不同的地方在于栈只能在栈顶操作，因此一般在应用单调栈的地方不限定栈的大小，否则可能会造成元素无法进栈。
## 1.9单调队列
### Q1.9.a【引入】蒟蒻
某竞赛可以从一年级打到𝑘年级，每年有一个一年级新生开始打这个比赛。这竞赛很特殊，选手水平永远不变。

显然：每个选手有𝑘年的竞赛时间；

很多年后，每年都恰好有𝑘个选手正在打这个比赛。

问题来了：从第𝑘年开始的每一年，需要知道谁是现役最强。

如果一个人比你强，还比你小，那你就打不过她了。

nmd, wsm?

因为你没退役的时候，她肯定也没退役

所以你永远不可能是现役最强

**泥永无出头之日**
### Q1.9.a 分析
我们考虑每一年，拿一个队列来维护“有可能成为现役最强”的选手。对于每一年，干这些事：

-把队列末端所有比新选手菜的人弹掉
-把队首已经退役的选手弹掉
-此时的队首就是这一年的答案
-把新选手加入队列

e.g.样例: 

k=3, 

a[]= 3   1   2   4   6   1   2   5   3
 
q.push(3) -没人更菜，没人退役 栈3
		  -答案=3
		  -q.push(1)

		  -没人更菜，没人退役 栈3 1
		  -答案=3
		  -q.push(2)
	
		  -1更菜 栈3 2，没人退役
		  -答案=3
		  -q.push(4)
	
		  -3,2都菜 栈4，退役的挂了
		  -答案=4
		  -q.push(6)

		  -4更菜，弹出 栈6，退役的挂了
		  -答案=6
		  -q.push(1)

		  -没人更菜，退役的挂了 栈6 1
		  -答案=6
		  -q.push(2)

		  -1更菜 栈6 2，没人退役
		  -答案=6
		  -q.push(5)
 
		  -2更菜 栈6 5
		  -6退役了，栈5
		  -答案=5

**有n个节点的环=2遍序列+滑动窗口**