#  数据结构必备经法

多语言代码：

```java []
//java codes

```
```python []
# python codes

```
```c++ []
// c++ codes

```
```c []
// c codes

```

## 数据结构与算法心法

> **核心学习数据结构与算法**

 10 个数据结构：`数组、链表、栈、队列`（线性表）、散列表、二叉树、堆、跳表、图、Trie树

10 个算法：递归、排序、二分查找、搜索、哈希算法、贪心算法、分治算法、回溯算法、动态规划、字符串匹配算法

- **算法**是求解问题的一系列计算步骤，用来将输入数据转换成输出结果 `从蛮力到策略`
- **数据结构**是数据的组织与存储：`从杂乱无章到井然有序`
- **算法 + 数据结构 = 程序**

> 对于每一种数据结构或算法学习它的**“来历”“自身的特点”“适合解决的问题”以及“实际的应用场景”**,千万不要被动地记忆，要==多辩证地思考，多问为什么==。如果你一直这么坚持做，你会发现，等你学完之后，写代码的时候就会不由自主	地考虑到很多性能方面的事情，时间复杂度、空间复杂度非常高的垃圾代码出现的次数就会越来越少。你的编程内功就真正得到了修炼。

### 算法本质

计算机和数学不同，计算机算法的本质是==穷举==，而普遍认为比较难的算法，比如回溯算法、动态规划、DFS 算法等，它们的本质也是穷举，只不过需要借助递归的形式，或者说是递归的思想，来实现穷举。

穷举有两个关键难点：⽆遗漏、⽆冗余。遗漏，会直接导致答案出错；冗余，会拖慢算法的运⾏速度。所以，当你看到⼀道算法题，可以从这两个维度去思考：

1、如何穷举？即==无遗漏地穷举所有可能解==。

2、如何聪明地穷举？即==避免所有冗余的计算==，消耗尽可能少的资源求出答案。

不同类型的题⽬，难点是不同的，==有的题⽬难在「如何穷举」，有的题⽬难在「如何聪明地穷举」==。

什么算法的难点在「如何穷举」呢？⼀般是==递归类问题，最典型的就是动态规划系列问题==。

- 动态规划系列问题的核⼼原理⽆⾮就是==先写出暴⼒穷举解法（状态转移⽅程），加个备忘录就成⾃顶向下的递归解法了，再改⼀改就成⾃底向上的递推迭代解法==、

什么算法的难点在「如何聪明地穷举」呢？⼀些⽿熟能详的==⾮递归算法技巧，都可以归在这⼀类。==

这里主要就是各种技巧，比如贪心算法、KMP算法等等

综上所述，上述过程就是在不断优化算法的时间、空间复杂度，也就是所谓==「如何聪明地穷举」==。

注意的是：`「算法⼯程师」做的这个「数学算法」，和「数据结构与算法」中的这个「计算机算法」完全是两码事，`前者重点在数学建模和调参经验，计算机真就只是拿来做计算的⼯具⽽已；⽽后者的重点是计算机思维，需要你能够站在计算机的视⻆，抽象、化简实际问题，然后⽤合理的数据结构去解决问题。

#### 学习心法

对于任何数据结构，其基本操作⽆⾮==遍历== + ==访问（增删查改）==。即尽可能⾼效地增删查改。

数组遍历框架，典型的线性迭代结构，也具有递归结构，链表遍历框架，兼具迭代和递归结构。

```java []
//java codes
/* 迭代遍历数组 */
void traverse(int[] arr) {
    for (int i = 0; i < arr.length; i++) {

    }
}

/* 递归遍历数组 */
void traverse(int[] arr, int i) {
    if (i == arr.length) {
        return;
    }
    // 前序位置
    traverse(arr, i + 1);
    // 后序位置
}
--------------------------------------------------------------------
    
/* 基本的单链表节点 */
class ListNode {
    int val;
    ListNode next;
}

/* 迭代遍历单链表 */
void traverse(ListNode head) {
    for (ListNode p = head; p != null; p = p.next) {

    }
}

/* 递归遍历单链表 */
void traverse(ListNode head) {
    if (head == null) {
        return;
    }
    // 前序位置
    traverse(head.next);
    // 后序位置
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

# 迭代遍历数组
def traverse(arr: List[int]):
    for i in range(len(arr)):
        pass

# 递归遍历数组
def traverse(arr: List[int], i: int):
    if i == len(arr):
        return
    # 前序位置
    traverse(arr, i + 1)
    # 后序位置

--------------------------------------------------------
# 基本的单链表节点
class ListNode:
    def __init__(self, val):
        self.val = val
        self.next = None

# 迭代遍历单链表
def traverse(head: ListNode):
    p = head
    while p != None:
        p = p.next

# 递归遍历单链表
def traverse(head: ListNode):
    if head == None:
        return
    # 前序位置
    traverse(head.next)
    # 后序位置

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

//迭代遍历数组
void traverse(vector<int>& arr) {
    for (int i = 0; i < arr.size(); i++) {

    }
}

//递归遍历数组
void traverse(vector<int>& arr, int i) {
    if (i == arr.size()) {
        return;
    }
    //前序位置
    traverse(arr, i + 1);
    //后序位置
}

//迭代遍历单链表
void traverse(ListNode* head) {
    for (ListNode* p = head; p != nullptr; p = p -> next) {

    }
}

//递归遍历单链表
void traverse(ListNode* head) {
    if (head == nullptr) {
        return;
    }
    //前序位置
    traverse(head -> next);
    //后序位置
}

```
```c []
// c codes
typedef struct node{
	int data;
	struct node left;
    struct node right;
}node;
```

你也注意到了，==只要是递归形式的遍历，都可以有前序位置和后序位置，分别在递归之前和递归之后==，那么**所谓前序位置，就是刚进入一个节点（元素）的时候，后序位置就是即将离开一个节点（元素）的时候**，那么进一步，你把代码写在不同位置，代码执行的时机也不同，其中线性结构前序和后续位置见图：

<img src="https://labuladong.online/algo/images/%E4%BA%8C%E5%8F%89%E6%A0%91%E6%94%B6%E5%AE%98/1.jpeg" alt="img" style="zoom: 25%;" />

而**二叉树这种结构（**典型的⾮线性递归遍历结构）无非就是二叉链表，由于没办法简单改写成迭代形式，所以一般说`二叉树的遍历框架都是指递归的形式`。在这里二叉树递归遍历框架也是一样的，只不过多了一个中序位置罢了。

```java []
//java codes
/* 基本的二叉树节点 */
class TreeNode {
    int val;
    TreeNode left, right;
}

void traverse(node n){
    // 前序遍历
    traverse(n.left);
    // 中序遍历
    traverse(n.right);
    // 后序遍历
}
```
```python []
# python codes
# 基本的二叉树节点
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right
        
def traverse(root: TreeNode):
    // 前序遍历
    traverse(n.left);
    // 中序遍历
    traverse(n.right);
    // 后序遍历
```
```c++ []
// c++ codes
```
```c []
// c codes
```

前中后序三个位置迭代遍历位置在二叉树上是这样：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/2.jpeg" alt="img" style="zoom: 25%;" />

**前中后序是遍历二叉树过程中处理每一个节点的三个特殊时间点**，从图中可以看到每个节点都有「唯一」属于自己的前中后序位置，绝不仅仅是三个顺序不同的 List。

**二叉树的所有问题，就是让你在前中后序位置注入巧妙的代码逻辑，去达到自己的目的，你只需要单独思考每一个节点应该做什么，其他的不用你管，抛给二叉树遍历框架，递归会在所有节点上做相同的操作**。

而二叉树框架可以扩展为 N 叉树的遍历框架：

```java []
//java codes
/* 基本的 N 叉树节点 */
class TreeNode {
    int val;
    TreeNode[] children;
}

void traverse(TreeNode root) {
    for (TreeNode child : root.children)
        traverse(child);
}
```
```python []
# python codes
# 基本的 N 叉树节点
class TreeNode:
    val: int
    children: List[TreeNode]

def traverse(root: TreeNode) -> None:
    for child in root.children:
        traverse(child)

```
```c++ []
// c++ codes
```
```c []
// c codes
```

N 叉树的遍历⼜可以扩展为图的遍历（图就是好⼏ N 叉棵树的结合体），你说图是可能出现环的？⽤个布尔数组 visited 做标记就⾏了，

可以看到，[图论算法基础](https://labuladong.online/algo/data-structure/graph-traverse/) 把二叉树的遍历框架扩展到了图，并以遍历为基础实现了图论的各种经典算法。

总的来说，故所谓框架，就是套路。不管增删查改，这些代码都是永远⽆法脱离的结构，你可以把这个结构作为⼤纲，根据具体问题在框架上添加代码。

#### 学习路线

1、先学习像数组、链表这种基本数据结构的常⽤算法，⽐如单链表翻转，前缀和数组，⼆分搜索等。

因为这些算法属于会者不难难者不会的类型，难度不⼤，学习它们不会花费太多时间。⽽且这些⼩⽽美的算法经常让你⼤呼精妙，能够有效培养你对算法的兴趣。

2、学会基础算法之后，不要急着上来就刷回溯算法、动态规划这类笔试常考题，⽽应该先刷⼆叉树，先刷⼆叉树，先刷⼆叉树，重要的事情说三遍。

### 时间复杂度&空间复杂度分析

事后统计分析： 把代码跑一遍，通过统计、监控，就能得到算法执行的时间和占用的内存大小。（局限性大）

#### 时间复杂度分析

时间复杂度表示法，体现整体算法随着规模增大的趋势表现，也叫作渐进时间复杂度（asymptotic time complexity），简称时间复杂度。

1. 只关注循环最多的一段 代码
2. 加法原则：取量级最大的复杂度
3. 乘法原则：取量级结果最大的

其中算法复杂度运算规则如下：

1. 加法规则
   O(f(n))+O(g(n))=O(max(f(n),g(n)))
   O(f(n))+O(g(n))=O(f(n)+g(n))
   如果g(n)=O(f(n))，则O(f(n))+O(g(n))=O( (f(n))
2. 乘法规则
   O(f(n))*O(g(n))=O(f(n)*g(n))
   O(c*f(n))=O(f(n))，c是一个正常数
3. f(n)=O ( (f(n))

![Θ,O,Ω的图像表示](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/20211016202335.jpeg)

1）渐近符号的含义：**O（上界）、Ω（下界）、Θ（准确界）** 

2）运行时间记号的定义(设有函数 f(n)和 g(n)是定义在非负整数集合上的正函数)：

**大** **O** **记号**：存在正常数 c 和 n0 使得对所有n ≥ n0有：f(n) ≤ cg(n)，记为f(n) ∈ O(g(n))

- 例如：n ∈O(n2)、100n+5 ∈O(n2)、n(n-1)/2 ∈O(n2)

**大** **Ω** **记号**：存在正常数 c 和 n0 使得对所有n ≥ n0有：f(n) ≥ cg(n)，记为f(n) ∈ Ω(g(n))

- 例如：n3∈Ω (n2)、n(n+1)∈Ω (n2)、4n2+5 ∈Ω (n2)

**大Θ记号**：设有函数 f(n)和 g(n)是定义在非负整数集合上的正函数，如果存在正整数 n0和正常数c1 和 c2（c1 ≤c2），使得当 n≥n0 时，有 c1 g(n)≤f(n)≤c2 g(n) ，就称 f(n)的阶是 Θ(g(n))，则记做f(n)=Θ(g(n))

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231225103903739.png" alt="image-20231225103903739" style="zoom: 33%;" />

> 时间复杂度具有「最差」、「平均」、「最佳」三种情况，分别使用 O , Θ , Ω 三种符号表示。此外还有均摊时间复杂度（amortized timecomplexity）。「`平均则是引入概率论，均摊则是平摊思想`」

**根据从小到大排列，常见的算法时间复杂度主要有：**

**`O(1) ＜ O(log n) ＜ O(n) ＜ O(nlog n) ＜ O(n^2) ＜ O(n^3) < O(2^n) ＜ O(n!) ＜ O(n^n)`**

主要分为两类，**多项式量级**和**非多项式量级**。

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128154326858.png" alt="image-20231128154326858" style="zoom: 33%;" />

最常见的多项式时间算法的渐近时间复杂度。
        `O(1)＜O(log n)＜O(n)＜O(nlog n)＜O(n2)＜O(n3)`

最常见的非多项式量级算法的渐近时间复杂度。当数据规模 n 越来越大时，非多项式量级算法的执行时间会急剧增加，求解问题的执行时间会无限增长。所以，非多项式时间复杂度的算法其实是**非常低效**的算法。
        ` O(2n)＜O(n!)＜O(nn)`

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/20211016203924.png" alt="img" style="zoom:50%;" />

>  **渐进增长率比较**

方法1：**定义法**

找到正常数 c 和 n0 使得对所有n ≥ n0 有 f(n) ≤ cg(n)，则f(n) = O(g(n))

方法2：**极限法**

比较两个函数f(n)和g(n)的渐近增长率时，可以对两个函数相除，然后令变量 n 趋向于无穷，看这个极限值是无穷大还是一个大于零的常数还是趋向于0。

![image-20240531123205516](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240531123205516.png)

- 前两种情况意味着f(n) ∈ O(g(n))
- 后两种情况意味着f(n) ∈ Ω(g(n))
- 第二种情况意味着f(n) ∈ Θ(g(n))

方法3：**取对数法**

对于比较难的比较的两个函数，我们可以对它们同时取对数后再进行比较

参考文章：

https://jwt1399.top/posts/46989.html#toc-heading-9

#### 递归的时间复杂性分析

> 方法1：**主定理-递推方程求解**

主定理适用于求右边递归式算法的时间复杂度：**T(n) = aT(n/b) + f(n)**

其中：

- n：问题的规模大小
- a：原问题的子问题个数
- n/b：每个子问题的大小
- f(n)：将原问题分解成子问题和将子问题的解合并成原问题的解的时间

![image-20231226140437826](core%20algorithm.assets/image-20231226140437826.png)

方法2：**递归树方法（Recursion Tree）**

> **一切递归算法的本质都是一棵多叉树，你一定要用多叉树的视角去理解递归算法，这样才能形成框架思维**

在递归树中每一个节点表示一个单一子问题的代价，子问题对应某次递归函数的调用。我们将树中每层中的代价求和，得到每层的代价，然后将所有层的代价求和，得到所有递归调用的总代价。

以mergeSort为例：

$T(N)=2T(N/2) + \Theta(N)$
假设$\Theta(N)=aN$

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231226140816742.png" alt="image-20231226140816742" style="zoom:50%;" />

树的高度为$logN$
每层代价为$aN$
可得总代价=$aN(logN)$
根据Big-O定理，可得$T(N)=O(Nlog(N))$

例子：

<img src="core%20algorithm.assets/image-20231226145913563.png" alt="image-20231226145913563" style="zoom: 33%;" />

#### 空间复杂度分析

空间复杂度分析：时间复杂度的全称是渐进时间复杂度，表示算法的执行时间与数据规模之间的增长关系。类比一下，空间复杂度全称就是渐进空间复杂度（asymptotic spacecomplexity），表示算法的存储空间与数据规模之间的增长关系。

查看循环最多的变量生成的一段代码

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128154541062.png" alt="image-20231128154541062" style="zoom: 33%;" />

常见的复杂度并不多，从低阶到高阶有：O(1)、O(logn)、O(n)、O(nlogn)、O(n )。几乎都是这些

> 其中还有四种复杂度分析方法
>
> 最好情况时间复杂度（best case timecomplexity）、最坏情况时间复杂度（worst case time complexity）
>

## 核心数据结构

可以初步分为线性表或者非线性表

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128190250563.png" alt="image-20231128190250563" style="zoom: 33%;" />

与它相对立的概念是非线性表，比如二叉树、堆、图等。之所以叫非线性，是因为，在非线性表中，数据之间并不是简单的前后关系，遍历主要使用递归方法。

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128190420528.png" alt="image-20231128190420528" style="zoom: 33%;" />

数据结构的存储⽅式==只有两种==：数组（顺序存储）和链表（链式存储）

Redis 数据库的朋友可能也知道，Redis 提供列表、字符串、集合等等⼏种常⽤数据结构，但是对于每

种数据结构，底层的存储⽅式都⾄少有两种，以便于根据存储数据的实际情况使⽤合适的存储⽅式。

### 数组

数组（Array）是一种线性表数据结构。它用一组连续的内存空间，来存储一组具有相同类型的数据。由于数组有**连续的内存空间和相同类型的数据**,内存访问机制 - 任意访问(随机访问)

有这么一种说法,之所以数组下标从0开始, 是因为在内存访问机制中可以减少一次减号运算

从数组存储的内存模型上来看，“**下标”最确切的定义应该是“偏移（offset）**”。前面也讲到，如果用 a 来表示数组的首地址，a[0] 就是偏移为 0 的位置，也就是首地址，a[k] 就表示偏移 k 个 type_size 的位置，所以计算 a[k] 的内存地址只需要用这个公式：

> `a[k]_address = base_address + k * type_size`

与之对应的也有两个问题,插入数据和删除数据,需要移动大量的内存,而实际中的动态数组需要划出大量的内存块迁移,会导致内存碎片问题, 

在面对这个场景, JVM 标记清除垃圾回收算法的核心思想先记录下已经删除的数据。每次的删除操作并不是真正地搬移数据，只是记录数据已经被删除。当数组没有更多空间存储数据时，我们再触发执行一次真正的删除操作，这样就大大减少了删除操作导致的数据搬移。

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128190517761.png" alt="image-20231128190517761" style="zoom: 33%;" />

此外还要警惕数据越界问题,很多计算机病毒也正是利用到了代码中的数组越界可以访问非法地址的漏洞，来攻击系统，所以写代码的时候一定要警惕数组越界。

数组越界在 C 语言中是一种未决行为，并没有规定数组访问越界时编译器应该如何处理。因为，访问数组的本质就是访问一段连续内存，只要数组通过偏移计算得到的内存地址是可用的，那么程序就可能不会报任何错误。(也就是继续运行,你发现不了!!)

实际上,有很多容器已经被开发优化好,比如 Java 中的 ArrayList、C++ STL 中的vector。在项目开发中，ArrayList 最大的优势就是可以将很多数组操作的细节封装起来。比如前面提到的数组插入、删除数据时需要搬移其他数据等。另外，它还有一个优势，就是支持动态扩容(将空间自动扩容为 1.5 倍大小。)。不过，这里需要注意一点，因为扩容操作涉及内存申请和数据搬移，是比较耗时的。所以，如果事先能确定需要存储的数据大小，最好在创建 ArrayList 的时候事先指定数据大小。

1.Java ArrayList 无法存储基本类型，比如 int、long，需要封装为 Integer、Long 类，而Autoboxing、Unboxing 则有一定的性能消耗，所以如果特别关注性能，或者希望使用基本类型，就可以选用数组。

2.如果数据大小事先已知，并且对数据的操作非常简单，用不到 ArrayList 提供的大部分方法，也可以直接使用数组。

对于业务开发，直接使用容器就足够了，省时省力。毕竟损耗一丢丢性能，完全不会影响到系统整体的性能。但如果你是做一些非常底层的开发，比如开发网络框架，性能的优化需要做到极致，这个时候数组就会优于容器，成为首选。

优缺点：

数组由于是紧凑连续存储,可以随机访问，通过索引快速找到对应元素，⽽且相对节约存储空间。但正因为连续存储，内存空间必须⼀次性分配够，所以说数组如果要扩容，需要重新分配⼀块更⼤的空间，再把数据全部复制过去，时间复杂度 O(N)；⽽且你如果想在数组中间进⾏插⼊和删除，每次必须搬移后⾯的所有数据以保持连续，时间复杂度 O(N)。

### 链表

三种最常见的链表结构，它们分别是：单链表、双向链表和循环链表, 双向循环链表。由于链表性质, 一般不会出现内存碎片问题.

我们把内存块称为链表的“结点”。为了将所有的结点串起来，每个链表的结点除了存储数据之外，还需要记录链上的下一个结点的地址。如图所示，我们把这个记录下个结点地址的指针叫作后继指针next。

数组简单易用，在实现上使用的是连续的内存空间，可以借助 CPU 的缓存机制，**预读**数组中的数据，所以访问效率更高。而链表在内存中并不是连续存储，所以对 CPU 缓存不友好，没办法有效预读。

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231128191817122.png" alt="image-20231128191817122" style="zoom: 33%;" />

数组的缺点是大小固定，一经声明就要占用整块连续内存空间。如果声明的数组过大，系统可能没有足够的连续内存空间分配给它，导致“内存不足（out of memory）”。如果声明的数组过小，则可能出现不够用的情况。这时只能再申请一个更大的内存空间，把原数组拷贝进去，非常费时。链表本身没有大小的限制，天然地支持动态扩容，我觉得这也是它与数组最大的区别。(当我们往支持动态扩容的数组中插入一个数据时，如果数组中没有空闲空间了，就会申请一个更大的空间，将数据拷贝过去，而数据拷贝的操作是非常耗时的。)

如果你的代码对内存的使用非常苛刻，那数组就更适合你。因为链表中的每个结点都需要消耗额外的存储空间去存储一份指向下一个结点的指针，所以内存消耗会翻倍。而且，对链表进行频繁的插入、删除操作，还会导致频繁的内存申请和释放，容易造成内存碎片，如果是 Java 语言，就有可能会导致频繁的 GC（Garbage Collection，垃圾回收）。

代码要写好链表有以下几点：

1. 了解理解指针或引用的含义（地址调用）
2. 警惕指针丢失和内存泄漏：特别是在删除操作中，避免丢失和未释放资源
3. 利用哨兵机制简化链表代码

优缺点：

链表因为元素不连续，⽽是靠指针指向下⼀个元素的位置，所以不存在数组的扩容问题；如果知道某⼀元素的前驱和后驱，操作指针即可删除该元素或者插⼊新元素，时间复杂度 O(1)。但是正因为存储空间不连续，你⽆法根据⼀个索引算出对应元素的地址，所以不能随机访问；⽽且由于每个元素必须存储指向前后元素位置的指针，会消耗相对更多的储存空间。

# 算法

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231225105424184.png" alt="image-20231225105424184" style="zoom:50%;" />

在解题中，我们根据问题运用所学的知识点即可，常见的问题一般都为判断问题和优化问题

- **判断问题**：是否存在一个…解
- **优化问题**：找出**最大/最小**的…解

很多经典的难问题都是优化问题，而一个优化问题往往可以转换成对应的判断问题。

1. 贪心算法：逐步建立一个解决方案，具体地优化一些局部准则。 自顶向下。
2. 分治算法：将一个问题分解成独立的子问题，求解每个子问题，并将子问题的解组合起来形成原问题的解。 自顶向下。
3. 动态规划：把一个问题分解成一系列相互重叠的子问题，并为越来越大的子问题建立解决方案。自底向上。

## 数组系列算法

单链表常考的技巧就是==双指针==，（聪明穷举和穷举都有）

数组常⽤的技巧有很大一部分还是==双指针==相关的技巧，说白了是教你如何聪明地进行穷举（数组无法递归，只能迭代，所以考点在如何聪明的穷举）

如：⼆分搜索技巧、滑动窗⼝算法技巧、前缀和技巧 和 差分数组技巧

主要算法技巧是双指针，双指针⼜分为==中间向两端扩散的双指针、两端向中间收缩的双指针、快慢指针==。此外，数组还有==前缀和和差分数组==也属于必知必会的算法技巧

### 前缀和数组

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [303. Range Sum Query - Immutableopen in new window](https://leetcode.com/problems/range-sum-query-immutable/) | [303. 区域和检索 - 数组不可变open in new window](https://leetcode.cn/problems/range-sum-query-immutable/) |  🟢   |
| [304. Range Sum Query 2D - Immutableopen in new window](https://leetcode.com/problems/range-sum-query-2d-immutable/) | [304. 二维区域和检索 - 矩阵不可变open in new window](https://leetcode.cn/problems/range-sum-query-2d-immutable/) |  🟠   |
|                              -                               | [剑指 Offer II 013. 二维子矩阵的和open in new window](https://leetcode.cn/problems/O4NDxx/) |  🟠   |

**前缀和主要适用的场景是`原始数组不会被修改`的情况下，频繁查询某个`区间`的累加和**。

核心思路是提前计算所需的结果（复杂度O（n）需要遍历一次），并通过简单的运算（如加减乘除）得到结果，使其算法复杂度为O（1），就好比我们在生活收拾好东西，方便拿取。

#### ⼀维数组中的前缀和

见⼒扣第 303 题「[区域和检索 - 数组不可变](https://leetcode.cn/problems/range-sum-query-immutable/)」，让你计算数组区间内元素的和，这是⼀道标准的前缀和问题：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240529160430611.png" alt="image-20240529160430611" style="zoom:33%;" />

`sumRange` 函数需要计算并返回一个索引区间之内的元素和，没学过前缀和的人可能写出如下代码：

```java
def sumRange(self, left: int, right: int) -> int:
        res = 0
        for i in range(left, right+1):
            res += self.nums[i]
        return res
```

`sumRange` 方法会被频繁调用，而它的时间复杂度是 `O(N)`，其中 `N` 代表 `nums` 数组的长度。

前缀和技巧，可将 `sumRange` 函数的时间复杂度降为 `O(1)`

```java []
//java codes
class NumArray {
    // 前缀和数组
    private int[] preSum;

    /* 输入一个数组，构造前缀和 */
    public NumArray(int[] nums) {
        // preSum[0] = 0，便于计算累加和
        preSum = new int[nums.length + 1];
        // 计算 nums 的累加和
        for (int i = 1; i < preSum.length; i++) {
            preSum[i] = preSum[i - 1] + nums[i - 1];
        }
    }
    
    /* 查询闭区间 [left, right] 的累加和 */
    public int sumRange(int left, int right) {
        return preSum[right + 1] - preSum[left];
    }
}

```
```python []
# python codes
class NumArray:
    def __init__(self, nums: List[int]):
        # 前缀和数组
        self.preSum = [0] * (len(nums) + 1)
        # 计算 nums 的累加和
        for i in range(1, len(self.preSum)):
            self.preSum[i] = self.preSum[i - 1] + nums[i - 1]

    def sumRange(self, left: int, right: int) -> int:
        # 查询闭区间 [left, right] 的累加和
        return self.preSum[right + 1] - self.preSum[left]
```
```c++ []
// c++ codes
```
```c []
// c codes
```

这个技巧在生活中运用也挺广泛的，比方说，你们班上有若干同学，每个同学有一个期末考试的成绩（满分 100 分），那么请你实现一个 API，输入任意一个分数段，返回有多少同学的成绩在这个分数段内。

那么，你可以先通过计数排序的方式计算每个分数具体有多少个同学，然后利用前缀和技巧来实现分数段查询的 API：

```java
int[] scores; // 存储着所有同学的分数
// 试卷满分 100 分
int[] count = new int[100 + 1]
// 记录每个分数有几个同学
for (int score : scores)
    count[score]++
// 构造前缀和
for (int i = 1; i < count.length; i++)
    count[i] = count[i] + count[i-1];

// 利用 count 这个前缀和数组进行分数段查询

```

#### 二维矩阵中的前缀和

力扣第 304 题「[二维区域和检索 - 矩阵不可变](https://leetcode.cn/problems/range-sum-query-2d-immutable/)」，其实和上一题类似，上一题是让你计算子数组的元素之和，这道题让你计算二维矩阵中子矩阵的元素之和：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240531090616328.png" alt="image-20240531090616328" style="zoom: 50%;" />

显然，若是暴力解法，需要嵌套循环（O（n^2)复杂度），我们想一想一维数组前缀和的思想，提前算好相关的结果，通过简单运算（加减乘除）得到所需结果。

提示一下：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240531090732612.png" alt="image-20240531090732612" style="zoom: 33%;" />

子矩阵的元素和可以转化成它周边==⼏个⼤矩阵的元素和的运算==（`需要注意是可以互相转换(等式要敏感)，例如绿色矩阵就可以由行列减1的矩阵之和减去重叠部分得到`），这四个⼤矩阵有⼀个共同的特点，就是==左上⻆都是 (0, 0) 原点==。故我们可以维护⼀个⼆维 preSum 数组，专⻔记录以原点为顶点的矩阵的元素之和，就可以⽤⼏次加减运算算出任何⼀个⼦矩阵的元素和。

```java []
//java codes
class NumMatrix {
    // 定义：preSum[i][j] 记录 matrix 中子矩阵 [0, 0, i-1, j-1] 的元素和
    private int[][] preSum;
    
    public NumMatrix(int[][] matrix) {
        int m = matrix.length, n = matrix[0].length;
        if (m == 0 || n == 0) return;
        // 构造前缀和矩阵
        preSum = new int[m + 1][n + 1];
        for (int i = 1; i <= m; i++) {
            for (int j = 1; j <= n; j++) {
                // 计算每个矩阵 [0, 0, i, j] 的元素和
                preSum[i][j] = preSum[i-1][j] + preSum[i][j-1] + matrix[i - 1][j - 1] - preSum[i-1][j-1];
            }
        }
    }
    
    // 计算子矩阵 [x1, y1, x2, y2] 的元素和
    public int sumRegion(int x1, int y1, int x2, int y2) {
        // 目标矩阵之和由四个相邻矩阵运算获得
        return preSum[x2+1][y2+1] - preSum[x1][y2+1] - preSum[x2+1][y1] + preSum[x1][y1];
    }
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

class NumMatrix:
    # 定义：preSum[i][j] 记录 matrix 中子矩阵 [0, 0, i-1, j-1] 的元素和
    def __init__(self, matrix: List[List[int]]):
        m, n = len(matrix), len( matrix[0])
        if m == 0 or n == 0: return
        # 构造前缀和矩阵
        self.preSum = [[0 for _ in range(n+1)] for _ in range(m+1)]
        for i in range(1, m+1):
            for j in range(1, n+1):
                # 计算每个矩阵 [0, 0, i, j] 的元素和
                self.preSum[i][j] = self.preSum[i-1][j] + self.preSum[i][j-1] + matrix[i-1][j-1] - self.preSum[i-1][j-1]

    # 计算子矩阵 [x1, y1, x2, y2] 的元素和
    def sumRegion(self, x1: int, y1: int, x2: int, y2: int) -> int:
        # 目标矩阵之和由四个相邻矩阵运算获得
        return self.preSum[x2+1][y2+1] - self.preSum[x1][y2+1] - self.preSum[x2+1][y1] + self.preSum[x1][y1]

```
```c++ []
// c++ codes

```
```c []
// c codes
```



这样，`sumRegion` 函数的时间复杂度也用前缀和技巧优化到了 O(1)，这是典型的「==空间换时间==」思路。

实际运用中还是要多培养自己的思维灵活性，做到一眼看出题目是一个前缀和问题。除了本文举例的基本用法，==前缀和数组经常和其他数据结构或算法技巧相结合==，我会在 [前缀和技巧高频习题](https://labuladong.online/algo/problem-set/perfix-sum/) 中举例讲解。

### 差分数组

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [1094. Car Poolingopen in new window](https://leetcode.com/problems/car-pooling/) | [1094. 拼车open in new window](https://leetcode.cn/problems/car-pooling/) |  🟠   |
| [1109. Corporate Flight Bookingsopen in new window](https://leetcode.com/problems/corporate-flight-bookings/) | [1109. 航班预订统计open in new window](https://leetcode.cn/problems/corporate-flight-bookings/) |  🟠   |
| [370. Range Additionopen in new window](https://leetcode.com/problems/range-addition/)🔒 | [370. 区间加法open in new window](https://leetcode.cn/problems/range-addition/)🔒 |  🟠   |

**差分数组的主要适用场景是频繁对`原始数组的某个区间的元素进行增减`**。（核心思想便是提前计算好差分数组，通过差分数组与原数组之前的等式关系，从而只需要一次操作便可以对某个区间的元素进行增减）

场景：比如说，我给你输入一个数组 `nums`，然后又要求给区间 `nums[2..6]` 全部加 1，再给 `nums[3..9]` 全部减 3，再给 `nums[0..4]` 全部加 2，再给...，一通操作猛如虎，然后问你，最后 `nums` 数组的值是什么？若是使用暴力解，则需要O(N)。 这个时候我们就可以使用和前缀和思想非常类似的算法技巧「==差分数组==」，

类似前缀和技巧构造的 `preSum` 数组，我们先对 `nums` 数组构造一个 `diff` 差分数组，**`diff[i]` 就是 `nums[i]` 和 `nums[i-1]` 之差**。此时通过这个 `diff` 差分数组是可以反推出原始数组 `nums` 的。

代码逻辑如下：

```java []
for i in lengh(array)
    diff[0] = nums[0] //差分数组第一个值等于数组第一个值
    diff[i] = nums[i] - nums[i-1] //差分数组
   	ori[i] = ori[i-1] + diff[i] // 原数组，可以从上一行推出来 nums[i] = diff[i] + nums[i-1]
```

这样构造差分数组 `diff`，就可以快速进行区间增减的操作，如果你想对区间 `nums[i..j]` 的元素全部加 3，那么只需要让 `diff[i] += 3`，然后再让 `diff[j+1] -= 3` 即可，原理很简单，`diff[i] += 3` 意味着给 `nums[i..]` 所有的元素都加了 3，然后 `diff[j+1] -= 3` 又意味着对于 `nums[j+1..]` 所有元素再减 3，那综合起来，是不是就是对 `nums[i..j]` 中的所有元素都加 3 了？

只要花费 O(1) 的时间修改 `diff` 数组，就相当于给 `nums` 的整个区间做了修改。多次修改 `diff`，然后通过 `diff` 数组反推，即可得到 `nums` 修改后的结果。

把差分数组抽象成一个类，包含 `increment` 方法和 `result` 方法，代码如下：

```java []
//java codes
// 差分数组工具类
class Difference {
    // 差分数组
    private int[] diff;
    
    /* 输入一个初始数组，区间操作将在这个数组上进行 */
    public Difference(int[] nums) {
        assert nums.length > 0;
        diff = new int[nums.length];
        // 根据初始数组构造差分数组
        diff[0] = nums[0];
        for (int i = 1; i < nums.length; i++) {
            diff[i] = nums[i] - nums[i - 1];
        }
    }

    /* 给闭区间 [i, j] 增加 val（可以是负数）*/
    public void increment(int i, int j, int val) {
        diff[i] += val;
        if (j + 1 < diff.length) {
            diff[j + 1] -= val;
        }
    }

    /* 返回结果数组 */
    public int[] result() {
        int[] res = new int[diff.length];
        // 根据差分数组构造结果数组
        res[0] = diff[0];
        for (int i = 1; i < diff.length; i++) {
            res[i] = res[i - 1] + diff[i];
        }
        return res;
    }
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

# 差分数组工具类
class Difference:
    # 差分数组
    def __init__(self, nums: List[int]):
        assert len(nums) > 0
        self.diff = [0] * len(nums)
        # 根据初始数组构造差分数组
        self.diff[0] = nums[0]
        for i in range(1, len(nums)):
            self.diff[i] = nums[i] - nums[i - 1]

    # 给闭区间 [i, j] 增加 val（可以是负数）
    def increment(self, i: int, j: int, val: int) -> None:
        self.diff[i] += val
        if j + 1 < len(self.diff):
            self.diff[j + 1] -= val

    # 返回结果数组
    def result(self) -> List[int]:
        res = [0] * len(self.diff)
        # 根据差分数组构造结果数组
        res[0] = self.diff[0]
        for i in range(1, len(self.diff)):
            res[i] = res[i - 1] + self.diff[i]
        return res

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

// 差分数组工具类
class Difference {
    // 差分数组
    private:
        int* diff;
    
    /* 输入一个初始数组，区间操作将在这个数组上进行 */
    public:
        Difference(int* nums, int length) {
            assert(length > 0);
            diff = new int[length]();
            diff[0] = nums[0];
            for (int i = 1; i < length; i++) {
                diff[i] = nums[i] - nums[i - 1];
            }
        }

        /* 给闭区间 [i, j] 增加 val（可以是负数）*/
        void increment(int i, int j, int val) {
            diff[i] += val;
            if (j + 1 < sizeof(diff) / sizeof(diff[0])) {
                diff[j + 1] -= val;
            }
        }

        /* 返回结果数组 */
        int* result() {
            int* res = new int[sizeof(diff) / sizeof(diff[0])]();
            res[0] = diff[0];
            for (int i = 1; i < sizeof(diff) / sizeof(diff[0]); i++) {
                res[i] = res[i - 1] + diff[i];
            }
            return res;
        }
};

```
```c []
// c codes
```

注意一下 `increment` 方法中的 if 语句，当 `j+1 >= diff.length` 时，说明是对 `nums[i]` 及以后的整个数组都进行修改，那么就不需要再给 `diff` 数组减 `val` 了。

## 链表系列算法

链表定义：



### 单链表的基本技巧

单链表基本代码（要先定义好节点，在定义链表）：

```java []
//java codes
```
```python []
# python codes
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    # 添加元素到链表头部
    def add_first(self, data):
        new_node = Node(data)
        new_node.next = self.head
        self.head = new_node

    # 打印链表
    def print_list(self):
        current = self.head
        while current:
            print(current.data, end=" ")
            current = current.next
        print()
```
```c++ []
// c++ codes
```
```c []
// c codes
```

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [141. Linked List Cycleopen in new window](https://leetcode.com/problems/linked-list-cycle/) | [141. 环形链表open in new window](https://leetcode.cn/problems/linked-list-cycle/) |  🟢   |
| [142. Linked List Cycle IIopen in new window](https://leetcode.com/problems/linked-list-cycle-ii/) | [142. 环形链表 IIopen in new window](https://leetcode.cn/problems/linked-list-cycle-ii/) |  🟠   |
| [160. Intersection of Two Linked Listsopen in new window](https://leetcode.com/problems/intersection-of-two-linked-lists/) | [160. 相交链表open in new window](https://leetcode.cn/problems/intersection-of-two-linked-lists/) |  🟢   |
| [19. Remove Nth Node From End of Listopen in new window](https://leetcode.com/problems/remove-nth-node-from-end-of-list/) | [19. 删除链表的倒数第 N 个结点open in new window](https://leetcode.cn/problems/remove-nth-node-from-end-of-list/) |  🟠   |
| [21. Merge Two Sorted Listsopen in new window](https://leetcode.com/problems/merge-two-sorted-lists/) | [21. 合并两个有序链表open in new window](https://leetcode.cn/problems/merge-two-sorted-lists/) |  🟢   |
| [23. Merge k Sorted Listsopen in new window](https://leetcode.com/problems/merge-k-sorted-lists/) | [23. 合并K个升序链表open in new window](https://leetcode.cn/problems/merge-k-sorted-lists/) |  🔴   |
| [86. Partition Listopen in new window](https://leetcode.com/problems/partition-list/) | [86. 分隔链表open in new window](https://leetcode.cn/problems/partition-list/) |  🟠   |
| [876. Middle of the Linked Listopen in new window](https://leetcode.com/problems/middle-of-the-linked-list/) | [876. 链表的中间结点open in new window](https://leetcode.cn/problems/middle-of-the-linked-list/) |  🟢   |
|                              -                               | [剑指 Offer 22. 链表中倒数第k个节点open in new window](https://leetcode.cn/problems/lian-biao-zhong-dao-shu-di-kge-jie-dian-lcof/) |  🟢   |
|                              -                               | [剑指 Offer 25. 合并两个排序的链表open in new window](https://leetcode.cn/problems/he-bing-liang-ge-pai-xu-de-lian-biao-lcof/) |  🟢   |
|                              -                               | [剑指 Offer 52. 两个链表的第一个公共节点open in new window](https://leetcode.cn/problems/liang-ge-lian-biao-de-di-yi-ge-gong-gong-jie-dian-lcof/) |  🟢   |
|                              -                               | [剑指 Offer II 021. 删除链表的倒数第 n 个结点open in new window](https://leetcode.cn/problems/SLwz0R/) |  🟠   |
|                              -                               | [剑指 Offer II 022. 链表中环的入口节点open in new window](https://leetcode.cn/problems/c32eOV/) |  🟠   |
|                              -                               | [剑指 Offer II 023. 两个链表的第一个重合节点open in new window](https://leetcode.cn/problems/3u1WK4/) |  🟢   |
|                              -                               | [剑指 Offer II 078. 合并排序链表open in new window](https://leetcode.cn/problems/vvXgSW/) |  🔴   |

单链表有很多巧妙的操作，本⽂就总结⼀下单链表的基本技巧，每个技巧都对应着⾄少⼀道算法题

1、合并两个有序链表

2、链表的分解

3、合并 k 个有序链表

4、寻找单链表的倒数第 k 个节点

5、寻找单链表的中点

6、判断单链表是否包含环并找出环起点

7、判断两个单链表是否相交并找出交点

这些解法都⽤到了==双指针技巧==，所以说对于单链表相关的题⽬，双指针的运⽤是⾮常⼴泛的，下⾯我们就来⼀个⼀个看。

#### 合并两个有序链表

这是最基本的链表技巧，⼒扣第 21 题「[合并两个==有序==链表](https://leetcode.cn/problems/merge-two-sorted-lists/)」（如果无序的话，可以对链表进行依次排序）就是这个问题：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240531101412568.png" alt="image-20240531101412568" style="zoom:33%;" />

代码逻辑如下：

```java []
//java codes
ListNode mergeTwoLists(ListNode l1, ListNode l2) {
    // 虚拟头结点
    ListNode dummy = new ListNode(-1), p = dummy;
    ListNode p1 = l1, p2 = l2;
    
    while (p1 != null && p2 != null) {
        // 比较 p1 和 p2 两个指针
        // 将值较小的的节点接到 p 指针
        if (p1.val > p2.val) {
            p.next = p2;
            p2 = p2.next;
        } else {
            p.next = p1;
            p1 = p1.next;
        }
        // p 指针不断前进
        p = p.next;
    }
    
    if (p1 != null) {
        p.next = p1;
    }
    
    if (p2 != null) {
        p.next = p2;
    }
    
    return dummy.next;
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

def mergeTwoLists(l1: ListNode, l2: ListNode) -> ListNode:
    # 虚拟头结点
    dummy = ListNode(-1)
    p = dummy
    p1 = l1
    p2 = l2

    while p1 and p2: 
        # 比较 p1 和 p2 两个指针
        # 将值较小的的节点接到 p 指针
        if p1.val > p2.val:
            p.next = p2
            p2 = p2.next
        else:
            p.next = p1
            p1 = p1.next
        # p 指针不断前进
        p = p.next

    if p1:
        p.next = p1

    if p2:
        p.next = p2

    return dummy.next

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

ListNode* mergeTwoLists(ListNode* l1, ListNode* l2) {
    // 虚拟头结点
    ListNode* dummy = new ListNode(-1), *p = dummy;
    ListNode* p1 = l1, *p2 = l2;
    
    while (p1 != NULL && p2 != NULL) {
        // 比较 p1 和 p2 两个指针
        // 将值较小的的节点接到 p 指针
        if (p1->val > p2->val) {
            p->next = p2;
            p2 = p2->next;
        } else {
            p->next = p1;
            p1 = p1->next;
        }
        // p 指针不断前进
        p = p->next;
    }
    
    if (p1 != NULL) {
        p->next = p1;
    }
    
    if (p2 != NULL) {
        p->next = p2;
    }
    
    return dummy->next;
}

```
```c []
// c codes
```

可视化面板（这个可视化非常详细，==每次是整个链表p1添加到尾部，而后前进p和p1两个指针，之后再次比较p1.p2，最后返回虚拟头节点的next，即合并指针==）：https://labuladong.online/algo/essential-technique/linked-list-skills-summary/#div_merge-two-sorted-lists

形象地理解，这个算法的逻辑类似于拉拉链，`l1, l2` 类似于拉链两侧的锯齿，指针 `p` 就好像拉链的拉索，将两个有序链表合并；或者说这个过程像蛋白酶合成蛋白质，`l1, l2` 就好比两条氨基酸，而指针 `p` 就好像蛋白酶，将氨基酸组合成蛋白质。

代码中还用到一个链表的算法题中是很常见的**「==虚拟头结点==」技巧，也就是 `dummy` 节点**。当你需要创造一条新链表的时候，可以使用虚拟头结点简化边界情况的处理。如果不使用 `dummy` 虚拟节点，代码会复杂一些，需要额外处理指针 `p` 为空的情况。而有了 `dummy` 节点这个占位符，可以避免处理空指针的情况，降低代码的复杂性

比如说，

**合并有序链表**：

- 不使用虚拟头结点时，你需要特别处理合并后的链表的头节点。如果两个链表中的一个为空，你需要将另一个链表的头节点设置为合并后链表的头节点。
- 使用虚拟头结点，你可以将合并操作的起始点设置为虚拟头结点的下一个节点，这样无论两个链表是否为空，你都可以从虚拟头结点的下一个节点开始合并，无需额外的边界检查。

**分解链表**：
- 如果你需要将一个链表分解成两个有序链表，不使用虚拟头结点时，你需要在分解过程中不断更新头节点的指针，以确保链表的连续性。
- 使用虚拟头结点，你可以从虚拟头结点开始操作，将分解后的链表的头节点直接连接到虚拟头结点的后面，简化了链表的连接和断开操作。

**反转链表**：
- 不使用虚拟头结点时，反转链表的头节点需要特别处理，因为第一个节点在反转后将成为最后一个节点。
- 使用虚拟头结点，你可以简单地从虚拟头结点的下一个节点开始反转，最后将原链表的最后一个节点（现在的第一个节点）设置为新链表的头节点。

**插入节点**：
- 在没有虚拟头结点的情况下，插入新节点到链表头部时，需要特别处理头节点的更新。
- 使用虚拟头结点，你可以将新节点插入到虚拟头结点和第一个实际节点之间，简化了插入操作。

**删除节点**：
- 如果需要删除链表的头节点，没有虚拟头结点时，你需要更新头节点指针到下一个节点。
- 使用虚拟头结点，删除操作可以统一处理，因为无论删除哪个节点，你都可以简单地将前一个节点的 `next` 指针指向要删除节点的 `next` 节点。

总的来说，虚拟头结点提供了一个统一的操作起点，使得链表的头部操作更加直观和简单，减少了对边界条件的检查和处理，从而简化了代码逻辑，提高了代码的可读性和可维护性。

#### [单链表的分解](https://labuladong.online/algo/essential-technique/linked-list-skills-summary/#单链表的分解)

力扣第 86 题「[分隔链表](https://leetcode.cn/problems/partition-list/)」：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20240531104933408.png" alt="image-20240531104933408" style="zoom: 50%;" />

在合并两个有序链表时让你合二为一，而这里需要分解让你把原链表一分为二。具体来说，我们可以把原链表分成两个小链表，一个链表中的元素大小都小于 `x`，另一个链表中的元素都大于等于 `x`，最后再把这两条链表接到一起，就得到了题目想要的结果。

整体逻辑和合并有序链表非常相似，细节直接看代码吧，注意虚拟头结点的运用：



## 二叉树系列算法

二叉树的算法思想的运用广泛，`甚至可以说，只要涉及递归，都可以抽象成二叉树的问题`。

注：函数命名习惯：二叉树中用遍历思路解题时函数签名一般是 `void traverse(...)`，没有返回值，靠更新外部变量来计算结果，而用==分解问题思路解题时函数名根据该函数具体功能而定，而且一般会有返回值，返回值是子问题的计算结果。==

与此对应的，你会发现我在 [回溯算法核心框架](https://labuladong.online/algo/essential-technique/backtrack-framework/) 中给出的函数签名一般也是没有返回值的 `void backtrack(...)`，而在 [动态规划核心框架](https://labuladong.online/algo/essential-technique/dynamic-programming-framework/) 中给出的函数签名是带有返回值的 `dp` 函数。这也说明它俩和二叉树之间千丝万缕的联系。

### 核心心法

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [104. Maximum Depth of Binary Treeopen in new window](https://leetcode.com/problems/maximum-depth-of-binary-tree/) | [104. 二叉树的最大深度open in new window](https://leetcode.cn/problems/maximum-depth-of-binary-tree/) |  🟢   |
| [144. Binary Tree Preorder Traversalopen in new window](https://leetcode.com/problems/binary-tree-preorder-traversal/) | [144. 二叉树的前序遍历open in new window](https://leetcode.cn/problems/binary-tree-preorder-traversal/) |  🟢   |
| [543. Diameter of Binary Treeopen in new window](https://leetcode.com/problems/diameter-of-binary-tree/) | [543. 二叉树的直径open in new window](https://leetcode.cn/problems/diameter-of-binary-tree/) |  🟢   |
|                              -                               | [剑指 Offer 55 - I. 二叉树的深度open in new window](https://leetcode.cn/problems/er-cha-shu-de-shen-du-lcof/) |  🟢   |

二叉树系列算法分为两种解题思维模式：

**1、是否可以通过遍历一遍二叉树得到答案**？如果可以，用一个 `traverse` 函数配合外部变量来实现，这叫「遍历」的思维模式。这种思路代表着回溯算法、DFS 算法等。

**2、是否可以定义一个递归函数，通过子问题（子树）的答案推导出原问题的答案**？如果可以，写出这个递归函数的定义，并==充分利用这个函数的返回值==，这叫「分解问题」的思维模式。这种思路代表着动态规划、分治算法等；

`在用动态规划/回溯算法等比较复杂的问题时，用树的视角来理解算法，只要把递归树画出来，就可以很直观地理解这些递归算法`

无论使用哪种思维模式，你都需要思考：

**如果单独抽出一个二叉树节点，它需要做什么事情？需要在什么时候（前/中/后序位置）做**？其他的节点不用你操心，递归函数会帮你在所有节点上执行相同的操作。

举一个算法的例子来理解：计算⼆叉树最⼤深度，实现 maxDepth 这个函数

**遍历递归⼀遍⼆叉树方法**（回溯算法核⼼框架为例）：

这里的遍历框架回想一下：

```c
typedef struct node{
	int data;
	struct node left;
    struct node right;
}node;

void traverse(node n){
    // 前序遍历
    traverse(n.left);
    // 中序遍历
    traverse(n.right);
    // 后序遍历
}
```



```java
//java codes
class Solution {

    // 记录最大深度
    int res = 0;
    int depth = 0;

    // 主函数
    int maxDepth(TreeNode root) {
        traverse(root);
        return res;
    }

    // 二叉树遍历框架
    void traverse(TreeNode root) {
        if (root == null) {
            // 到达叶子节点
            res = Math.max(res, depth);
            return;
        }
        // 前序遍历位置
        depth++;
        traverse(root.left);
        traverse(root.right);
        // 后序遍历位置
        depth--;
    }
}

```

```python []
# python codes
class Solution:
    def __init__(self):
        # 记录最大深度
        self.res = 0
        self.depth = 0
        
    def maxDepth(self, root: TreeNode) -> int:
        self.traverse(root)
        return self.res
        
    def traverse(self, root: TreeNode) -> None:
        if not root:
            # 到达叶子节点
            self.res = max(self.res, self.depth)
            return
        # 前序遍历位置
        self.depth += 1
        self.traverse(root.left)
        self.traverse(root.right)
        # 后序遍历位置
        self.depth -= 1
```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

class Solution {
public:

    // 记录最大深度
    int res = 0;
    int depth = 0;

    // 主函数
    int maxDepth(TreeNode* root) {
        traverse(root);
        return res;
    }

    // 二叉树遍历框架
    void traverse(TreeNode* root) {
        if (root == NULL) {
            // 到达叶子节点
            res = max(res, depth);
            return;
        }
        // 前序遍历位置
        depth++;
        traverse(root->left);
        traverse(root->right);
        // 后序遍历位置
        depth--;
    }
};

```
```c []
// c codes
```

注意，在做其他回溯算法的题时，框架都是一样的，回溯算法虽然简单粗暴效率低，但特别有用，因为如果你对一道题无计可施，回溯算法起码能帮你写一个暴力解捞点分对吧。

**通过分解问题计算答案**（动态规划核⼼框架为例）：

这里要求最大深度，那么是不是自顶向下可以分解为求其左右子树中深度较大的一个，而后将此问题一直递归下去到叶子节点，此时该叶子结点的最大深度初始化为1，自底向上返回）

```java []
//java codes
// 定义：输入根节点，返回这棵二叉树的最大深度
int maxDepth(TreeNode root) {
	if (root == null) {
		return 0;
	}
	// 递归计算左右子树的最大深度
	int leftMax = maxDepth(root.left);
	int rightMax = maxDepth(root.right);
	// 整棵树的最大深度
	int res = Math.max(leftMax, rightMax) + 1;

	return res;
}

```
```python []
# python codes
# 定义：输入根节点，返回这棵二叉树的最大深度
def maxDepth(root: TreeNode) -> int:
    if root is None:
        return 0
    # 递归计算左右子树的最大深度
    leftMax = maxDepth(root.left)
    rightMax = maxDepth(root.right)
    # 整棵树的最大深度
    res = max(leftMax, rightMax) + 1

    return res

```
```c++ []
// c++ codes
// 定义：输入根节点，返回这棵二叉树的最大深度
int maxDepth(TreeNode* root) {
    if (root == nullptr) {
        return 0;
    }
    // 递归计算左右子树的最大深度
    int leftMax = maxDepth(root->left);
    int rightMax = maxDepth(root->right);
    // 整棵树的最大深度
    int res = max(leftMax, rightMax) + 1;

    return res;
}

```
```c []
// c codes
```

注：`depth--;` 是在二叉树的遍历过程中用来维护当前节点的深度信息的。你把 `traverse` 理解成在二叉树上游走的一个指针）

- 如果不减1，`depth`将一直保持增加，这将导致无法正确地反映从根到叶子节点的路径长度。
- 递归返回后减1是为了“回溯”到上一层，确保`depth`正确地反映了当前节点相对于根节点的深度。

**如果你感受到最大深度这个问题两种解法的区别，那就趁热打铁，我问你，二叉树的前序遍历怎么写**？

这里当然可以用递归遍历的方法来做，但是其实前序遍历是有规律的，见图

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/1.jpeg" alt="img" style="zoom:33%;" />

那这不就可以==分解问题==了么，**一棵二叉树的前序遍历结果 = 根节点 + 左子树的前序遍历结果 + 右子树的前序遍历结果**。

```java []
//java codes
// 定义：输入一棵二叉树的根节点，返回这棵树的前序遍历结果
List<Integer> preorder(TreeNode root) {
    List<Integer> res = new LinkedList<>();
    if (root == null) {
        return res;
    }
    // 前序遍历的结果，root.val 在第一个
    res.add(root.val);
    // 后面接着左子树的前序遍历结果
    res.addAll(preorder(root.left));
    // 最后接着右子树的前序遍历结果
    res.addAll(preorder(root.right));
    return res;
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

from typing import List

# 定义：输入一棵二叉树的根节点，返回这棵树的前序遍历结果
def preorder(root: TreeNode) -> List[int]:
    res = []
    if not root:
        return res
    # 前序遍历的结果，root.val 在第一个
    res.append(root.val)
    # 后面接着左子树的前序遍历结果
    res.extend(preorder(root.left))
    # 最后接着右子树的前序遍历结果
    res.extend(preorder(root.right))
    return res

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

// 定义：输入一棵二叉树的根节点，返回这棵树的前序遍历结果
vector<int> preorder(TreeNode* root) {
    vector<int> res;
    if (root == NULL) {
        return res;
    }
    // 前序遍历的结果，root->val 在第一个
    res.push_back(root->val);
    // 后面接着左子树的前序遍历结果
    vector<int> left = preorder(root->left);
    // 最后接着右子树的前序遍历结果
    vector<int> right = preorder(root->right);
    res.insert(res.end(), left.begin(), left.end());
    res.insert(res.end(), right.begin(), right.end());
    return res;
}

```
```c []
// c codes
```

这就是用分解问题的思维模式写二叉树的前序遍历，如果写中序和后序遍历也是类似的。

中序和后序遍历也是类似的，只要把 `add(root.val)` 放到中序和后序对应的位置就行了。

这个解法短小精干，但为什么不常见呢？

一个原因是**这个算法的复杂度不好把控**，比较依赖语言特性。

Java 的话无论 ArrayList 还是 LinkedList，`addAll` 方法的复杂度都是 O(N)，所以总体的最坏时间复杂度会达到 O(N^2)，除非你自己实现一个复杂度为 O(1) 的 `addAll` 方法，底层用链表的话是可以做到的，因为多条链表只要简单的指针操作就能连接起来。

最主要的原因还是因为教科书上从来没有这么教过……

上文举了两个简单的例子，但还有不少二叉树的题目是可以==同时使用两种思路来思考和求解的==，这就要靠你自己多去练习和思考，==不要仅仅满足于一种熟悉的解法思路==。

综上，遇到一道二叉树的题目时的通用思考过程是：

**1、是否可以通过遍历一遍二叉树得到答案**？如果可以，用一个 `traverse` 函数配合外部变量来实现。

**2、是否可以定义一个递归函数，通过子问题（子树）的答案推导出原问题的答案**？如果可以，写出这个递归函数的定义，并==充分利用这个函数的返回值==。

**3、无论使用哪一种思维模式，你都要明白二叉树的每一个节点需要做什么，需要在什么时候（前中后序）做**。

#### 后序遍历

说后序位置之前，先简单说下中序和前序。

中序位置主要用在 二叉搜索树（Binary Search Tree，简称 BST）场景中，你完全可以把 BST 的中序遍历认为是遍历有序数组。

前序位置本身其实没有什么特别的性质，之所以你发现好像很多题都是在前序位置写代码，实际上是因为我们习惯把那些对前中后序位置不敏感的代码写在前序位置罢了。

你可以发现，前序位置的代码执行是自顶向下的，而后序位置的代码执行是自底向上的

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/2.jpeg" alt="img" style="zoom: 25%;" />

这里面大有玄妙，意味着前序位置的代码`只能从函数参数中获取父节点传递来的数据`，而后序位置的代码不仅可以获取参数数据，还可以获取到`子树通过函数返回值传递回来的数据`。

举具体的例子，现在给你一棵二叉树，我问你两个简单的问题：

1、如果把根节点看做第 1 层，如何打印出每一个节点所在的层数？

2、如何打印出每个节点的左右子树各有多少节点？

显然第一个可以用前文求最大深度，随着节点指针访问的depth输出得到，第二个问题由于前序遍历无法知道左右子树的节点，可以通过后序遍历子树返回值得到，即可以分解问题，当前节点接收并利用了子树返回的信息，这就意味着你把原问题分解成了当前节点 + 左右子树的子问题。（通过返回值自底向上求解）

```java []
//java codes
// 定义：输入一棵二叉树，返回这棵二叉树的节点总数
int count(TreeNode root) {
    if (root == null) {
        return 0;
    }
    int leftCount = count(root.left);
    int rightCount = count(root.right);
    // 后序位置
    printf("节点 %s 的左子树有 %d 个节点，右子树有 %d 个节点",
            root, leftCount, rightCount);

    return leftCount + rightCount + 1;
}

```
```python []
# python codes
# 定义：输入一棵二叉树，返回这棵二叉树的节点总数
def count(root: TreeNode) -> int:
    if not root:
        return 0
    leftCount = count(root.left)
    rightCount = count(root.right)
    # 后序位置
    print(f"节点 {root} 的左子树有 {leftCount} 个节点，右子树有 {rightCount} 个节点")

    return leftCount + rightCount + 1
```
```c++ []
// c++ codes
// 定义：输入一棵二叉树，返回这棵二叉树的节点总数
int count(TreeNode* root) {
    if (root == nullptr) {
        return 0;
    }
    int leftCount = count(root->left);
    int rightCount = count(root->right);
    // 后序位置
    printf("节点 %s 的左子树有 %d 个节点，右子树有 %d 个节点",
            root->val, leftCount, rightCount);

    return leftCount + rightCount + 1;
}
```
```c []
// c codes
```

这两个问题的根本区别在于：一个节点在第几层，你==从根节点遍历过来的过程就能顺带记录==，用递归函数的参数就能传递下去；而以一个节点为根的整棵子树有多少个节点，你需要==遍历完子树之后才能数清楚，然后通过递归函数的返回值拿到答案==。而==只有后序位置才能通过返回值获取子树的信息==。

那么换句话说，一旦你发现==题目需要用到子树==，那大概率要给函数设置合理的定义和返回值，在后序位置写代码了。

#### 层序遍历

二叉树题型主要是用来培养递归思维的，而==层序遍历属于迭代遍历==，也比较简单，这里就过一下代码框架吧：

```java []
//java codes
// 输入一棵二叉树的根节点，层序遍历这棵二叉树
void levelTraverse(TreeNode root) {
    if (root == null) return;
    Queue<TreeNode> q = new LinkedList<>();
    q.offer(root);

    // 从上到下遍历二叉树的每一层
    while (!q.isEmpty()) {
        int sz = q.size();
        // 从左到右遍历每一层的每个节点
        for (int i = 0; i < sz; i++) {
            TreeNode cur = q.poll();
            // 将下一层节点放入队列
            if (cur.left != null) {
                q.offer(cur.left);
            }
            if (cur.right != null) {
                q.offer(cur.right);
            }
        }
    }
}

```
```python []
# python codes

# 输入一棵二叉树的根节点，层序遍历这棵二叉树
def levelTraverse(root: TreeNode):
    if not root:
        return
    
    q = deque()
    q.append(root)

    # 从上到下遍历二叉树的每一层
    while q:
        sz = len(q)
        # 从左到右遍历每一层的每个节点
        for i in range(sz):
            cur = q.popleft()
            # 将下一层节点放入队列
            if cur.left:
                q.append(cur.left)
            if cur.right:
                q.append(cur.right)
```
```c++ []
// c++ codes
// 输入一棵二叉树的根节点，层序遍历这棵二叉树
void levelTraverse(TreeNode* root) {
    if (root == nullptr) return;
    queue<TreeNode*> q;
    q.push(root);

    // 从上到下遍历二叉树的每一层
    while (!q.empty()) {
        int sz = q.size();
        // 从左到右遍历每一层的每个节点
        for (int i = 0; i < sz; i++) {
            TreeNode* cur = q.front();
            q.pop();
            // 将下一层节点放入队列
            if (cur->left != nullptr) {
                q.push(cur->left);
            }
            if (cur->right != nullptr) {
                q.push(cur->right);
            }
        }
    }
}
```
```c []
// c codes
```

这里面 while 循环和 for 循环分管从上到下和从左到右的遍历：

<img src="https://labuladong.online/algo/images/dijkstra/1.jpeg" alt="img" style="zoom: 25%;" />

后文 [BFS 算法框架](https://labuladong.online/algo/essential-technique/bfs-framework/) 就是从二叉树的层序遍历扩展出来的，常用于求无权图的**最短路径**问题。

当然这个框架还可以灵活修改，题目不需要记录层数（步数）时可以去掉上述框架中的 for 循环，比如后文 [Dijkstra 算法](https://labuladong.online/algo/data-structure/dijkstra/) 中计算加权图的最短路径问题，详细探讨了 BFS 算法的扩展。

值得一提的是，有些很明显需要用层序遍历技巧的二叉树的题目，也可以用递归遍历的方式去解决，而且技巧性会更强，非常考察你对前中后序的把控。

关于层序遍历（以及其扩展出的 [BFS 算法框架](https://labuladong.online/algo/essential-technique/bfs-framework/)），我在最后多说几句。

如果你对二叉树足够熟悉，可以想到很多方式通过递归函数得到层序遍历结果，比如下面这种写法：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```python
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

from typing import List

class Solution:
    res: List[List[int]] = []

    def levelTraverse(self, root: TreeNode) -> List[List[int]]:
        if not root:
            return self.res
        # root 视为第 0 层
        self.traverse(root, 0)
        return self.res

    def traverse(self, root: TreeNode, depth: int) -> None:
        if not root:
            return
        # 前序位置，看看是否已经存储 depth 层的节点了
        if len(self.res) <= depth:
            # 第一次进入 depth 层
            self.res.append([])
        # 前序位置，在 depth 层添加 root 节点的值
        self.res[depth].append(root.val)
        self.traverse(root.left, depth + 1)
        self.traverse(root.right, depth + 1)
```

这种思路从结果上说确实可以得到层序遍历结果，但其本质还是二叉树的前序遍历，或者说 DFS 的思路，而不是层序遍历，或者说 BFS 的思路。因为这个解法是依赖前序遍历自顶向下、自左向右的顺序特点得到了正确的结果。

**抽象点说，这个解法更像是从左到右的「列序遍历」，而不是自顶向下的「层序遍历」**。所以对于计算最小距离的场景，这个解法完全等同于 DFS 算法，没有 BFS 算法的性能的优势。

还有优秀读者评论了这样一种递归进行层序遍历的思路：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```python
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

class Solution:
    res = []

    def levelTraverse(self, root: TreeNode) -> List[List[int]]:
        # 如果根节点为空，返回结果列表
        if not root:
            return self.res
        # 定义节点列表，并加入根节点，开始层序遍历
        nodes = [root]
        self.traverse(nodes)
        # 返回结果列表
        return self.res

    def traverse(self, curLevelNodes: List[TreeNode]) -> None:
        # 如果当前层节点为空，退出当前递归层
        if not curLevelNodes:
            return
        # 前序位置，计算当前层的节点值和下一层的节点列表
        nodeValues = []
        nextLevelNodes = []
        for node in curLevelNodes:
            nodeValues.append(node.val)
            if node.left:
                nextLevelNodes.append(node.left)
            if node.right:
                nextLevelNodes.append(node.right)
        # 前序位置添加结果，可以得到自顶向下的层序遍历
        self.res.append(nodeValues)
        self.traverse(nextLevelNodes)
        # 后序位置添加结果，可以得到自底向上的层序遍历结果
        # self.res.append(nodeValues)
```

这个 `traverse` 函数很像递归遍历单链表的函数，其实就是把二叉树的每一层抽象理解成单链表的一个节点进行遍历。

相较上一个递归解法，这个递归解法是自顶向下的「层序遍历」，更接近 BFS 的奥义，可以作为 BFS 算法的递归实现扩展一下思维。



总的来说，上述这些算法的本质都是穷举二（多）叉树，有机会的话通过剪枝或者备忘录的方式减少冗余计算，提高效率，就这么点事儿。

~~除了动归、回溯（DFS）、分治，还有一个常用算法就是 BFS 了， [BFS 算法核心框架](https://labuladong.online/algo/essential-technique/bfs-framework/) 就是根据二叉树的层序遍历代码改装出来的。~~

~~**更进一步，图论相关的算法也是二叉树算法的延续**。~~

~~比如 [图论基础](https://labuladong.online/algo/data-structure/graph-traverse/)，[环判断和拓扑排序](https://labuladong.online/algo/data-structure/topological-sort/) 和 [二分图判定算法](https://labuladong.online/algo/data-structure/bipartite-graph/) 就用到了 DFS 算法；再比如 [Dijkstra 算法模板](https://labuladong.online/algo/data-structure/dijkstra/)，就是改造版 BFS 算法加上一个类似 dp table 的数组。~~

## 递归算法&分治算法

比如 [分治算法详解](https://labuladong.online/algo/practice-in-action/divide-and-conquer/) 中说到的运算表达式优先级问题，其核心依然是大问题分解成子问题，==只不过没有重叠子问题，不能用备忘录去优化效率罢了==（分治算法问题是独立的）。

> 递归与分治的定义

**递归**：一个算法直接地或间接地调用自己本身，简称自己调用自己

【所能解决问题的特征】

可分解为一个或多个**相同**子问题，递归有限性（一定的递归次数），有界性（有结束递归的条件）

**分治**：将难以直接解决的大问题，分割成一些规模较小的相同问题，以便各个击破，分而治之。

【所能解决问题的特征】

（1）该问题的**规模缩小到一定的程度**就可以容易地解决；

（2）该问题可以分解为若干个规模较小的相同问题，即该问题具有**最优子结构性质**；

（3）利用该问题分解出的**子问题的解可以合并**为该问题的解；

（4）该问题所分解出的各个**子问题是相互独立**的，即子问题之间不包含公共的子问题。

> 递归与分治的算法思想

**递归法思想**：

通过函数调用自身将问题转化为本质相同但规模较小的子问题，是分治策略的具体体现。

**分治法思想**：

将一个规模为 n 的问题分解为 k 个规模较小的子问题，这些子问题互相独立且与原问题相同。

递归地解这些子问题，然后将各子问题的解合并得到原问题的解，自底向上逐步求出原来问题。

> 1）分治法的基本步骤：
>
> （1）划分：将原问题分解为若干个规模较小，相互独立，与原问题形式相同的子问题；
>
> （2）求解子问题：若子问题规模较小而容易被解决则直接解，否则递归地解各个子问题；
>
> （3）合并：将各个子问题的解合并为原问题的解。
>
> 2）分治法的启发式规则（原则）
>
> （1）**平衡子问题**：最好使子问题的规模大致相同。
>
> （2）**独立子问题**：各子问题之间相互独立



#### 经典算法

经典算法如下：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231226143849657.png" alt="image-20231226143849657" style="zoom:67%;" />

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/image-20231226144007170.png" alt="image-20231226144007170" style="zoom: 50%;" />

![image-20231226144029881](core%20algorithm.assets/image-20231226144029881.png)

还有快速算法、大数乘法（分治求解，减少乘法次数）等等，以下为经典算法的时间复杂度。

![image-20231226144354146](core%20algorithm.assets/image-20231226144354146.png)

> 重点补充
>
> 1）快速排序算法的性能
>
> 快速排序算法的效率与 轴值的选择 和 划分子序列的平衡性 有关
>
> 快速排序算法的性能取决于 **划分的对称性**
>
> 2）各问题求解时所用方法或算法
>
> 递归：排列问题，整数划分问题，Hanoi 塔问题
>
> 分治策略：二分搜索技术，大整数乘法，矩阵乘法，棋盘覆盖，合并排序，快速排序，线性时间选
>
> 择，最接近点对问题，循环赛日程表。
>
> 【例题 1】快速排序算法是基于 `分治策略 `的一种排序算法。
>
> 【例题 2】从分治法的一般设计模式可以看出，用它设计出的程序一般是` 递归算法` 。

## 动态规划

后⽂ 动态规划核⼼套路 阐述了动态规划系列问题的核⼼原理，⽆⾮就是先写出暴⼒穷举解法（状态转移⽅

程），加个备忘录就成⾃顶向下的递归解法了，再改⼀改就成⾃底向上的递推迭代解法了，动态规划的降维

打击 ⾥也讲过如何分析优化动态规划算法的空间复杂度。



动态规划系列问题有「最优子结构」和「重叠子问题」两个特性，而且大多是让你求最值的。很多算法虽然不属于动态规划，但也符合分解问题的思维模式。

比如 [分治算法详解](https://labuladong.online/algo/practice-in-action/divide-and-conquer/) 中说到的运算表达式优先级问题，其核心依然是大问题分解成子问题，只不过没有重叠子问题，不能用备忘录去优化效率罢了。



动态规划问题分析是自顶而下的思路，但是算法实现却是自底而上的策略。

动态规划与分治法类似，都是把大问题拆分成小问题，通过寻找大问题与小问题的递推关系，解决一个个小问题，最终达到解决原问题的效果。

但不同的是，分治法在子问题和子子问题等上被重复计算了很多次，而动态规划则具有记忆性，通过填写表把所有已经解决的子问题答案纪录下来，在新问题里需要用到的子问题可以直接提取，避免了重复计算，从而节约了时间，所以在问题满足最优性原理之后，用动态规划解决问题的核心就在于填表，表填写完毕，最优解也就找到。

> **本章重点：**
>
> - 理解动态规划算法的思想。
> - 对相应问题能建立基本的递归关系式并用从底至上的方法来求解，在求解过程中知道如何建立数据储存的表格。
> - 重点掌握的问题：带权重的活动安排问题、**0-1背包问题**、**最长公共子序列问题**、**矩阵连乘的最优计算次序问题**。
> - 理解0-1背包问题的动态规划算法不是多项式时间算法。

> 动态规划算法的基本步骤

（1）找出最优解的性质，并刻画其结构特征。

（2）递归地定义最优值。

（3）以自底向上的方式计算出最优值。

（4）根据计算最优值时得到的信息，构造最优解。

> 动态规划的算法思想

将待求解问题分解成若干个子问题，先求解子问题，然后从这些子问题的解得到原问题的解，

【适用条件】**分解得到的子问题往往不是相互独立的**

> 动态规划算法的基本要素

动态规划算法的两个基本要素是. **最优子结构性质** 和 **重叠子问题性质**

> 动态规划法的变形： **备忘录方法**
>
> 【区别】动态规划算法是 **自底向上** ，备忘录方法（和递归）算法的是 **自顶向下** 。
>
> 动态规划每个子问题都要解一次，但不会求解重复子问题；备忘录方法只解哪些确实需要解的子问题；递归方法每个子问题都要解一次，包括重复子问题。
>
> > 备忘录方法的控制结构与直接递归方法的控制结构相同，区别在于备忘录方法为每个解过的子问题建立了备忘录以备需要时查看，避免了相同子问题的重复求解。

#### 经典算法

##### 矩阵连乘问题

> 矩阵连乘的计算次数与计算顺序的关系

假设有一个p*q规模的矩阵A，一个q*r规模的矩阵B，并且我们现在再加上一个规模为r*s的矩阵C，那么这三个矩阵的乘积ABC有两种计算顺序：

 （AB）C
   A（BC）

对于第一种计算顺序来说，总共需要的计算次数为：

因为AB共需要计算【p*q*r】次，并且生成一个规模为【p*r】的中间矩阵，这个中间矩阵再与矩阵C相乘，又需要计算【p*r*s】次，并且生成一个规模为【p*s】的矩阵，这个矩阵也就是最后的结果，因此，按照第一种顺序计算，一共需要的计算次数如下：

$mult[(AB)C] = pqr+prs$

同理，按照第二种计算顺序，我们一共需要计算下面这么多次：

$mult[A(BC)] = qrs+pqs$

假设p=5,q=4,r=6并且s=2，则：

![img](core%20algorithm.assets/20190730111806740.png)

按照第一种计算顺序，我们需要计算180次，而按照第二种计算顺序，我们只需要计算88次就够了！！但是这两种顺序计算出来的矩阵的值却始终是一样的，真是太神奇了，计算顺序竟然能够影响所需要的计算次数，**因此，对于矩阵连乘来说，计算顺序是非常重要的！**

> **问题描述：**给定 n 个矩阵 {A1,A2,…,An} ，其中 Ai 与 Ai+1 是可乘的，用加括号的方法表示矩阵连乘的次序，不同加括号的方法所对应的计算次序是不同的，求矩阵连乘的最佳计算次序。
>
>
> 问题需要我们找出最少的计算次数，就是需要我们找到“正确”的计算顺序！

1. **分析最优子结构**，在本问题中，即找出如何划分“括号”的方法。

将矩阵连乘的积 **Ai Ai+1 … Aj** 简记为`A[i][j]` ，**Ai** 的维度记为 **pi-1 × pi**，那么上述问题变为求解 `A[1][n]`的最佳计算次序。

`A[1][n]的最佳计算次序：`设这个计算次序在矩阵 AK (1≤k<n) 和 AK+1 之间将矩阵链断开，则相应的加括号方式：( **Ai Ai+1 … Ak** )( **Ak+1Ai+1 … An** )，依此计算顺序，总计算量为 **Ai Ai+1 … Ak** 的计算量加上 **Ak+1Ai+1 … An** 的计算量，再加上 ( **Ai Ai+1 … Ak** ) 和 ( **Ak+1Ai+1 … An** )相乘的计算量。即 **`A[1][n] = A[1][k] + A[k+1][n] + pi-1 pk pn`**

> 此时问题的“最优子结构”就已经出现了，为了保证Ai...k*Ak+1...j是最优的计算顺序，则Ai...k和AK+1...j也应该是由“最优计算顺序”计算出来的，因此，我们就可以递归的调用这个过程。
> 假设Ai...k的计算顺序并不是最优的，那么我们可以用更好的计算顺序去替换，这样就产生了悖论。
> 同样的，如果Ak+1...j并不是最优的，那么我们可以在找出另外一个更好的计算顺序来替换他，此时也产生了悖论。

2.**建立最优子结构的递推式**

设计算 `A[i][j]` (i≤j) 所需的最少乘法次数为 `m[i][j]`，那么得到以下的递推公式（最少乘积次数则为【Ai...k所需要的最少乘积次数】+【Ai+1...j所需要的最少乘积次数】+【中间生成的两个临时矩阵所需要的乘积次数】）：

![img](core%20algorithm.assets/20190730222401675.png)

3. **自底向上计算最优质**

K的可能值也只有j-i种，因此我们就把这j-i都一个个的去试一遍，然后找出m[i,j]最小的那一个情况，此时的K值就是我们需要的，并且最小乘积次数也找到了，就是m[i,j]次。

计算m[i,j]时，我们必须首先得把![img](core%20algorithm.assets/20190731001913900.png)和![img](core%20algorithm.assets/20190731001924521.png)

给计算出来，才能够顺利的把![img](core%20algorithm.assets/2019073100200185.png)给计算出来。

对于被分割的两个子序列，对应的矩阵链的长度都小于![img](core%20algorithm.assets/2019073100222159.png)

因此，我们的算法以矩阵链长度增长的顺序来计算，就像下面这样子（假设我们需要计算m[1,n]）：

![img](core%20algorithm.assets/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzE5NzgyMDE5,size_16,color_FFFFFF,t_70.png)

例如，要计算矩阵连乘积A1A2A3A4A5A6，其中各矩阵的维数分别为:

| A1    | A2    | A3   | A4   | A5    | A6    |
| :---- | :---- | :--- | :--- | :---- | :---- |
| 30x35 | 35x15 | 15x5 | 5x10 | 10x20 | 20x25 |

依据递推公式，按照图 a 的次序，计算出 `m[i][j]`

![img](core%20algorithm.assets/image-20211011130742451.png)

![img](https://img.jwt1399.top//img/20211011131609.png)

本题是求解 `A[1][6]` 的最佳计算次序，即求`m[1][6]` 。由图 b 可知， `m[1][6] =15125`，因此矩阵连乘积A1A2A3A4A5A6 的最优值为 **15125**

4. **构造`最优解`**

若将对应`m[i][j]`的断开位置`k`记为`s[i][j]`，计算出最优值`m[i][j]`后，可递归地由`s[i][j]`[][]构造出相应的最优解。



![img](core%20algorithm.assets/20211011131648.png)



**例如**，**`m[2][5] = m[2][3] + m[4][5] + p1p3p5`** ，则 k = 3，因此 **`s[2][5] = 3`**

★最优解：

`s[1][6] = 3` ,因此矩阵链在A3和A4之间断开，则加括号方式为 **(A1A2A3)(A4A5A6 )**

`s[1][3] = 1`,因此矩阵链在A1和A2之间断开，则加括号方式为 **(A1(A2A3))(A4A5A6 )**

`s[4][6] = 5,`因此矩阵链在A5和A6之间断开，则加括号方式为 **(A1(A2A3))((A4A5)A6 )**

因此最优解为 **(A1(A2A3))((A4A5)A6 )**

```c++
#include <iostream>
using namespace std;
#define N 100
int s[N][N], m[N][N];  //s存储切割位置，m存储最优值 

void MatricChain(int *p , int n) {//p矩阵维数数组，n为矩阵个数
    for (int i = 1; i <= n; i++) {//初始化，对角线上的计算量和加括号的位置为0
        m[i][i] = 0;
        s[i][i] = 0;
    }
    for (int r = 2; r <= n; r++) {//r为矩阵链的长度
        for (int i = 1; i <= n - r + 1; i++) { //i为首矩阵的序号
            int j = i + r - 1; //j为尾矩阵的序号
            m[i][j] = m[i][i] + m[i + 1][j] + p[i - 1] * p[i] * p[j];//首先尝试在矩阵 i 处分开
            s[i][j] = i;
            for (int k = i + 1; k < j; k++) {  
                    int t = m[i][k] + m[k + 1][j] + p[i - 1] * p[k] * p[j]; // 然后尝试在矩阵 k 处分开 (i<=k<j)
                    if (t < m[i][j]) {
                        m[i][j] = t;
                        s[i][j] = k;
                    }
            }
        }
    }
}
void Traceback(int i, int j) {
    if (i == j) {
        return;
    }
    int k = s[i][j];
    Traceback(i, k); 
    Traceback(k + 1, j);
    cout << "A" << "[" << i << ":" << k << "]" << "×" << "A""[" << (k + 1) << ":" << j << "]"<<"  " ;
}

int main(){
    int p[] = {30,35,15,5,10,20,25};//矩阵维数
    int n = sizeof(p) / sizeof(int) - 1;//矩阵个数

    for(int i = 0; i < n; i++){
        cout << p[i]<<"×"<<p[i+1]<<"  ";
    }
    cout << "这" << n << "个矩阵连乘的最优值和最优解？" << endl;
    cout << endl;

    MatricChain(p,n);
    cout << "m[i][j]:" << endl;
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n; j++)
            cout << m[i][j] << "\t";
        cout << endl;
    }

    cout << endl;
    cout << "s[i][j]:" << endl;
    for (int i = 1; i <= n; i++) {
        for (int j = 1; j <= n; j++)
            cout << s[i][j] << "\t";
        cout << endl;
    }
    cout << endl;
    cout << "最少连乘次数(最优值):" << m[1][n] << "次。" << endl;
    cout << "最佳计算次序(最优解):" ;
    Traceback(1, n);
    cout << endl;
}
```

![img](core%20algorithm.assets/20211011231627.png)

##### 最长公共子序列

**问题描述︰**给定两个字符串，求解这两个字符串的最长公共子序列(LCS)。如: X={1,5,2,8,9,3,6},Y={5,6,8,9,3,7}，其最长公共子序列为{5,8,9,3}，最长公共子序列长度为4。那么如何求解呢？

[1143. 最长公共子序列 - 力扣（Leetcode）](https://leetcode.cn/problems/longest-common-subsequence/description/?envType=study-plan-v2&id=top-100-liked)

**1、分析最优子结构**

设序列 **X={x1, x2, …, xi}** 和 **Y={y1, y2, …, yj}** 的最长公共子序列为 **Z={z1, z2, …, zk}**，则

- ①若 **xi=yj** ，则 zk=xi=yj 且 **Zk-1** 是 Xi-1 和 Yj-1 的最长公共子序列;
- ②若 **xi≠yj** 且 **zk≠xi** ，则 **Zk** 是 Xi-1 和 Yj 的最长公共子序列;.
- ③若 **xi≠yj** 且 **zk≠yj** ，则 **Zk **是 Xi 和 Yj-1 的最长公共子序列。

**2、建立递推公式**

用**`c[i][j]`**表示 **Xi={x1, x2, …, xi}** 和 **Yj={y1, y2, …, yj}** 的最长公共子序列的长度，那么得到以下的递推公式：



![img](core%20algorithm.assets/20211010182558.png)

**3、计算`最优值`**

> 假设 X={A,B,C,E} 和 Y={B,D,C,E}

根据上方递推公式得到下表：

| `c[i][j]` | 1B   | 2D   | 3C   | 4E   |
| :-------- | :--- | :--- | :--- | :--- |
| **1A**    | 0    | 0    | 0    | 0    |
| **2B**    | 1    | 1    | 1    | 1    |
| **3C**    | 1    | 1    | 2    | 2    |
| **4E**    | 1    | 1    | 2    | `3`  |

在 `C[2][0]` 处，j = 0 ，此时根据公式`C[2][0]= 0`

在 `C[2][1]` 处，B = B，即 **xi=yj** ，此时根据公式`C[2][1]=C[1][0]+1=0+1=1`

在 `C[2][2]` 处，B ≠ C，即 **xi≠yj** ，此时根据公式`C[2][2]=max{C[2][1],C[1][2]}=1`

根据最**右下角的值(`c[][]`)**，我们可以知道**最长公共子序列长度为3**。

**4、构造`最优解`**

`b[i][j]`记录`c[i][j]`的值是由哪个子问题的解得到的

- `if(X[i]==Y[j])` 用b=1代表
- `if(X[i]!=Y[j])` 用b=2代表

| `b[i][j]` | 1B   | 2D   | 3C   | 4E   |
| :-------- | :--- | :--- | :--- | :--- |
| **1A**    | 2    | 2    | 2    | 2    |
| **2B**    | 1    | 2    | 2    | 2    |
| **3C**    | 2    | 2    | 1    | 2    |
| **4E**    | 2    | 2    | 2    | 1    |

| `c[i][j]` | 1B   | 2D   | 3C   | 4E   |
| :-------- | :--- | :--- | :--- | :--- |
| **1A**    | 0    | 0    | 0    | 0    |
| **2B**    | 1`↖` | 1`←` | 1    | 1    |
| **3C**    | 1    | 1    | 2`↖` | 2    |
| **4E**    | 1    | 1    | 2    | 3`↖` |

`↖`处则为最长公共子序列{B,C,E}

再来几个例题：

输入：X=<A,B,C,B,D,A,B>, Y=<B,D,C,A,B,A>，

| `c[i][j]` | **0** | **1B** | **2D** | **3C** | **4A** | **5B** | **6A** |
| --------- | ----- | ------ | ------ | ------ | ------ | ------ | ------ |
| **0**     | 0     | 0      | 0      | 0      | 0      | 0      | 0      |
| **1A**    | 0     | 0      | 0      | 0      | 1      | 1      | 1      |
| **2B**    | 0     | 1      | 1      | 1      | 1      | 2      | 2      |
| **3C**    | 0     | 1      | 1      | 2      | 2      | 2      | 2      |
| **4B**    | 0     | 1      | 1      | 2      | 2      | 3      | 3      |
| **5D**    | 0     | 1      | 2      | 2      | 2      | 3      | 3      |
| **6A**    | 0     | 1      | 2      | 2      | 3      | 3      | 4      |
| **7B**    | 0     | 1      | 2      | 2      | 3      | 4      | 4      |

解：长度为4

`b[i][j]`记录`c[i][j]`的值是由哪个子问题的解得到的

- `if(X[i]==Y[j])` 用↖代表

| `b[i][j]` | 1B               | 2D             | 3C             | 4A           | 5B             | 6A               |
| --------- | ---------------- | -------------- | -------------- | ------------ | -------------- | ---------------- |
| 1A        | **B** [1,1]      | B  [1,2]       | B  [1,3]       | B  [1,4]   ↖ | B  [1,5]       | B  [1,6]   ↖     |
| [2B][2B]  | ` B  [2,1]   ↖ ` | B  [2,2]       | B  [2,3]       | B  [2,4]     | B  [2,5]   ↖   | B  [2,6]         |
| [3C][]    | B  [3,1]         | B  [3,2]       | `B  [3,3]   ↖` | B  [3,4]  ←  | B  [3,5]       | B  [3,6]         |
| [4B][]    | B  [4,1]    ↖    | B  [4,2]       | B  [4,3]       | B  [4,4]     | `B  [4,5]   ↖` | B  [4,6]         |
| 5D        | B  [5,1]         | B  [5,2  ]   ↖ | B  [5,3]       | B  [5,4]     | B  [5,5]    ↑  | B  [5,6]         |
| [6A][]    | B  [6,1]         | B  [6,2]       | B  [6,3]       | B  [6,4]   ↖ | B  [6,5]       | `B  [6,6]   ↖  ` |
| 7B        | B  [7,1  ]   ↖   | B  [7,2]       | B  [7,3]       | B  [7,4]     | B  [7,5]    ↖  | B  [7,6]    ↑    |

即 B, C, B, A 

##### 0-1背包问题

> **问题描述：**有n个物品，它们有各自的重量 wi 和价值 vi ，现有给定容量为 C 的背包，如何让背包里装入的物品具有最大的价值总和？
>
> > 在选择装入背包中的物品时，对每种物品 i 只有两种选择，即装入或者不装入背包。不能将物品 i装入背包多次，也不能只装入物品 i 的部分。所以也叫 0-1背包问题，即一个特殊的整数规划问题。

![img](core%20algorithm.assets/1.png)

**1、分析最优子结构**

定义一个参数：`OPT(i,w)`

`OPT(i,w)`表示表示前 i 个物品 ( 1,2,3,…,i )的最大价值，i（当前背包存放物品的数量）、w（当前背包容量）

OPT(i,w) 显然有两种方案：

- ①不选择 i 物品
  - 如果不选择 i 物品，原问题退化成 **OPT(i-1，w)**，即包的剩余容量比 i 物品重量小，装不下，此时的价值与前 i-1 个的价值是一样的，从(1,2,3…i-1)中找最优解
- ②选择 i 物品
  - 如果选择 i 物品，原问题退化成 **vi + OPT(i-1，w-wi)**，即既然选择了 i 物品，能装的重量减少 wi，并尝试 i-1 是否装入

**2、建立递推公式**

递推公式如下：



![img](core%20algorithm.assets/202111111714615.png)



**3、计算`最优值`、构造`最优解`**

例如：给定如下 5 个物品的价值 vi 和重量 wi，限制包的容量 C 为11



![img](core%20algorithm.assets/202111111714596.png)



依据递推公式，计算出`OPT(i,w)`

![img](core%20algorithm.assets/202111111714543.png)

OPT(2,2) = max{ v2 + OPT(1,2-w2)，OPT(1,2)} = max{6，1} = 6

…

OPT(3,5) = max{ v3 + OPT(2,5-w3)，OPT(2,5)} = max{18，7} = 18

OPT(4,11) = max{ v4 + OPT(3,11-w4)，OPT(3,11)} = max{40，25} = 40

OPT(5,11) = max{ v5 + OPT(4,11-w5)，OPT(4,11)} = max{35，40} = 40

**因此最大价值为 40，由图中红线回溯可知，背包装了物品 3 和 4**

又例如：



<img src="core%20algorithm.assets/image-20231227110303444.png" alt="image-20231227110303444" style="zoom:67%;" />

则最大价值为 6，

m[1,6]>m[2,6]故第一件物品选中，将 c 更新为 c-w1=6-2=4

m[2,4]=m[3,4]故第二件物品未选中，c 值保留不变为 4

m[3,4]>0 故第三件物品被选中

故装入背包的物品有 1 和 3

- 加餐

 



> 问题的 **最优子结构性质** 是该问题可用动态规划算法或贪心算法求解的关键特征。
>
> 动态规划和分治法在分解子问题方面的不同点是 **前者分解出的子问题有重叠的，而后者分解出的**
>
> **子问题是相互独立（不重叠）的**
>
> 动态规划和分治法的相同点是 **两者都是将待求解问题分解成若干个子问题，先求解子问题，然后**
>
> **从这些子问题的解得到原问题的解** 

参考文章：

https://blog.csdn.net/qq_19782019/article/details/94356886

https://labuladong.github.io/algo/di-er-zhan-a01c6/bei-bao-le-34bd4/jing-dian--28f3c/

https://jwt1399.top/posts/46989.html#toc-heading-57

## 贪心算法

顾名思义，贪心算法总是作出在当前看来最好的选择。也就是说贪心算法并不从整体最优考虑，它所作出的选择只是在某种意义上的局部最优选择。虽然贪心算法不能对所有问题都得到整体最优解，但对许多问题它能产生整体最优解。如单源最短路径问题，最小生成树问题等。在一些情况下，即使贪心算法不能得到整体最优解，其最终结果却是最优解的很好近似。贪心算法就是用计算机模拟一个「贪心的人」来做出决策。这个贪心的人是目光短浅的，他每次总是：

- 只做出**当前看来最好的选择**
- **只看眼前的利益，而不考虑做出选择后对未来造成的影响**
- 并且他一旦做出了选择，就**没有办法反悔**（不可回溯）

`总结：`在对问题求解时，总是做出在**当前最好的选择**。也就是说并**不从整体最优考虑**，他所做出的是在某种意义上的**局部最优解**。 因此贪心算法不是对**所有问题**都能得到整体最优解。

> 贪心算法的基本要素是 贪心选择性质 和 最优子结构性质 
>
> **贪心选择性质**：指所求问题的**整体最优解可以通过一系列局部最优的选择，即贪心选择来达到**。
>
> **最优子结构性质**：当一个问题的**最优解包含其子问题的最优**解时，称此问题具有最优子结构性质。

贪心算法则通常以自顶向下的方式进行，以迭代的方式作出相继的贪心选择，每作一次贪心选择就将所求问题简化为规模更小的子问题。 

**应用场景**

解决一个问题需要多个步骤，每一个步骤有多种选择。**想清楚局部最优，想清楚全局最优，感觉局部最优是可以推出全局最优，并想不出反例，那么就试一试贪心**。

**解题步骤**

贪心算法一般分为如下三步：

- **1.分解：**将问题分解为若干个子问题
- **2.解决：**找出适合的贪心策略，求解每一个子问题的最优解
- **3.合并：**将局部最优解堆叠成全局最优解

#### 正确性证明

对于一个具体问题，要确定它是否具有贪心选择性质，必须证明每一步所作的贪心选择最终导致问题的整体最优解。**贪心算法最难的部分不在于问题的求解，而在于正确性的证明**，一般考虑某个子问题的最优解，然后考虑用一个贪心选择替换其中某个选择，修改此解，导出更小子问最优子结构同动态规划，而且其实一般也不是特别需要证明，关键还是在证明问题具有**贪心选择性质**。

> 如果在算法领域，遇到了需要使用数学证明的问题，通常首先想到的是使用两种方式，这两种方式分别是数学归纳法和反证法。
>
> 数学归纳法相当于是递推的过程，就像动态规划的过程，将基本的问题解决之后，假设规模为n的问题可以解决，就能推导出规模为n+1这样的问题。对于数学归纳法所适用的领域，通常都是有一个变量n在逐渐增加的过程。
>
> 反证法假设它不正确，然后看可不可能推导出矛盾。

![image-20231227112752826](core%20algorithm.assets/image-20231227112752826.png)

1. 假设贪心算法得到的解不是最优解，假设 S1 是贪心算法得到的解，S2 是所有最优解中和 S1 具有最多相同元素的解；
2. 比较 S1 和 S2，观察 S1 和 S2 中第一个（最前面一个）不一样的元素；
3. 在解 S2 中将不一样的元素换成 S1 中的那个元素得到另一个最优解 S3，这样 S3 和 S1 比 S2 和 S1有更多相同元素，和假设 S2 是与 S1 有最多相同元素的最优解矛盾，这样来推导 S1 是最优解。

贪心算法最优性证明例题
首先我们引入一个问题Interval Scheduling（调度问题）

> 操作系统进程调度算法中，短作业优先可以使**平均等待时间**最小，（平均等待时间是n个进程等待CPU时间的总和除以n）。证明该算法具有贪心选择性质

现在我们有一组请求 request = {1, 2, 3, … , n}，requesti的开始时间是starti，结束时间是endi，我们的目标是从集合request中选出尽可能多的不重合的request。

```
贪心算法通常都是很自然的思路，我们可以想到

总是选择最先开始的request，这样可以使我们的资源更早的投入使用。
总是选择持续时间最短的request，这样可以使我们的资源更快的被释放，这样可以使更多的请求被接受。
总是选择冲突最少的request，这样可以使得我们拒绝更少的request。
总是选择最先结束的request。
对于每一个贪心策略，我们都需要证明它是否能够一步一步的到达最优解。
```

> 1. 我们可以首先**声明一个最优解O**。
> 2. 如果在**第一步**，可以证明贪心策略不比最优解差。
> 3. 我们假设**第k步**，贪心策略的选择也不必最优解差。
> 4. 那么我们只要证明第k+1步，贪心策略的选择也可以接受，那么就说明贪心策略可以达到最优解。
>    可以给出最优性证明。

我们期望证明它得到的可以接受的request数是A，最优解得到的可以接受的request数是O，如果我们可以证明A === O，那么就说明这个贪心策略将会得到最优解。

接下来，我们假设A中的第i个request的结束时间是endi，O中第i个request(请求)的结束时间是Endi，如果我们可以证明endi不迟于Endi，那么贪心策略会是最优的。

1. 当i === 1，因为贪心策略选择的是所有request中最早结束的request，所以end1必然不迟于End1。

2. 我们假设当i === k时，endk也不迟于Endk。

3. 我们现在要证明当i === k + 1时，endk+1不迟于Endk+1

   因为贪心策略始终选择剩下的（没有被拒绝，也没有被接受的）request中的最早完成的，又因为前一步中endk不迟于Endk，所以对于第k+1步，贪心策略也必然选择不迟于最优解的request，这样我们就证明贪心策略的最优性。

​	

> 其中在动规之间二者的区别是
>
> 对于0-1背包问题，贪心选择之所以不能得到最优解是因为在这种情况下，它无法保证最终能将背包装满，部分闲置的背包空间使每公斤背包空间的价值降低了。事实上，在考虑0-1背包问题时，应**比较选择该物品和不选择该物品所导致的最终方案，然后再作出最好选择。由此就导出许多互相重叠的子问题**。这正是该问题可用动态规划算法求解的另一重要特征。

#### 经典算法

最小生成树的Prim算法（`从初始点开始找到的路径最短`）Prim算法利用 贪心  策略求解  最小生成树  问题，其时间复杂度是 O(n2)    

最小生成树的Kruskal算法（`全局路径最短`）

>  当图的边数为e时，Kruskal算法所需的计算时间是 O(eloge) 。当 e = Ω(n^2)    时，Kruskal算法比Prim算法差，但当e = O(n^2)时，Kruskal算法却比Prim算法好得多。

单源最短路径的Dijkstra算法。

##### Dijkstra算法

荷兰杰出计算机科学家、软件工程师 [Dr. Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra) 创建并发布了这个算法。

1959 年，他发表了一篇 3 页的文章《A note on two problems in connexion with graphs》来介绍他的新算法。

在 2001 年的一次采访中，Dijkstra 博士透露了他设计这个算法的起因和过程：

> 从 Rotterdam 到 Groningen 的最短路线是什么？我花了大概 20 分钟时间设计了这个寻找最短路径的算法。一天早上我正和我年轻的未婚妻在 Amsterdam 逛街，觉得有点累了，我们就坐在咖啡厅的露台上喝了一杯咖啡，我在想是否能够解决这个问题，然后，我设计出了这个最短路径算法。我说过，这是一个 20 分钟的设计。事实上，三年之后的 1959 年它才被发布，现在看来依然很不错，其原因之一是我当时设计的时候没有纸和笔，从而不得不极力避免所有可避免的复杂性。最终，令我惊讶的是，这个算法成为了我成名的基石之一。——引自文章[《An interview with Edsger W. Dijkstra》](https://dl.acm.org/doi/pdf/10.1145/1787234.1787249)

- Dijkstra 算法能够寻找出图中指定节点（“源节点”）到所有其他节点的最短路径。
- Dijkstra 算法利用边的权重来做计算，寻找源节点到所有其他节点的总距离最短（总权重最小）的路径。

##### Huffman编码

霍夫曼编码是一种无前缀编码。解码时不会混淆。其主要应用在数据压缩，加密解密等场合。

假如我有A,B,C,D,E五个字符，出现的频率（即权值）分别为5,4,3,2,1,那么我们第一步先取两个**最小权值**作为左右子树构造一个新树，即取1，2构成新树，其结点为1+2=3，如图：

![image](core%20algorithm.assets/0z710sycxq.png)

虚线为新生成的结点，第二步再把**新生成的权值为3的结点放到剩下的集合**中，所以集合变成{5,4,3,3}，再根据第二步，**取最小的两个权值构成新树**，如图：

![image](core%20algorithm.assets/yt5xtlfvo4.png)

再依次建立哈夫曼树，如下图：

![image](core%20algorithm.assets/7exutdvazl.jpeg)

其中各个权值替换对应的字符即为下图：

![image](core%20algorithm.assets/4bkr6a4l7p.jpeg)

所以各字符对应的编码为：A->11,B->10,C->00,D->011,E->010

再来一个例子

<img src="core%20algorithm.assets/image-20231227152039789.png" alt="image-20231227152039789" style="zoom:67%;" />



## 回溯法

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [46. Permutationsopen in new window](https://leetcode.com/problems/permutations/) | [46. 全排列open in new window](https://leetcode.cn/problems/permutations/) |  🟠   |
| [51. N-Queensopen in new window](https://leetcode.com/problems/n-queens/) | [51. N 皇后open in new window](https://leetcode.cn/problems/n-queens/) |  🔴   |
| [52. N-Queens IIopen in new window](https://leetcode.com/problems/n-queens-ii/) | [52. N皇后 IIopen in new window](https://leetcode.cn/problems/n-queens-ii/) |  🔴   |
|                              -                               | [剑指 Offer II 083. 没有重复元素集合的全排列open in new window](https://leetcode.cn/problems/VvJkup/) |  🟠   |

回溯法的==应用场景主要用于找到所有可能的解或满足条件的解==，具有“通用解题法”之称。~~回溯法是一种既带有 系统性 又带有 跳跃性 的搜索算法。~~

回溯法是一种**选优搜索法**，按选优条件向前搜索，以达到目标。但当探索到某一步时，发现原先选择并不优或达不到目标，就退回一步重新选择，==这种走不通就退回再走的技术为`回溯法`==，而==满足回溯条件的某个状态的点称为“回溯点”==。（有点类似启发式搜索，不过回退为回溯）

其实回溯算法和我们常说的 DFS 算法非常类似，本质上就是一种暴力穷举算法。回溯算法和 DFS 算法的细微差别是：`回溯算法是在遍历「树枝」，DFS 算法是在遍历「节点」`。

抽象地说，解决一个回溯问题，实际上就是遍历一棵决策树（解空间树或问题的状态空间树）的过程，树的每个叶子节点存放着一个可能的答案。你把整棵树遍历一遍，把叶子节点上的答案都收集起来，就能得到最终的合法答案。

站在回溯树的一个节点上，你只需要思考 3 个问题：

1、路径：也就是已经做出的选择。

2、选择列表：也就是你当前可以做的选择。

3、结束条件：也就是到达决策树底层，无法再做选择的条件。

回溯算法的框架的伪代码：

```python
# python codes
result = []
def backtrack(路径, 选择列表):
    if 满足结束条件:
        result.add(路径)
        return
    
    for 选择 in 选择列表: # 这里的选择列表可以理解为多个分叉，即多叉树
        # 做选择
        将该选择从节点的选择列表属性移除
        路径.add(选择)
        backtrack(路径, 选择列表)
        # 撤销选择
        路径.remove(选择)
        将该选择再加入此节点的选择列表属性


```

**其核心就是 for 循环里面的递归，在递归调用之前「做选择」，在递归调用之后「撤销选择」**，特别简单。

下面我们就通过「全排列」这个问题来解开之前的疑惑，详细探究一下其中的奥妙！

### [全排列问题](https://labuladong.online/algo/essential-technique/backtrack-framework/#一、全排列问题)

 力扣第 46 题「[全排列](https://leetcode.cn/problems/permutations/)」就是给你输入一个数组 `nums`，让你返回这些数字的全排列。（这次讨论的全排列问题不包含重复的数字）

我们在高中的时候就做过排列组合的数学题，我们也知道 `n` 个不重复的数，全排列共有 `n!` 个。那么我们当时是怎么穷举全排列的呢？

比方说给三个数 `[1,2,3]`，你肯定不会无规律地乱穷举，一般是这样：

先固定第一位为 1，然后第二位可以是 2，那么第三位只能是 3；然后可以把第二位变成 3，第三位就只能是 2 了；然后就只能变化第一位，变成 2，然后再穷举后两位……

其实这就是回溯算法，我们高中无师自通就会用，或者有的同学直接画出如下这棵回溯树（排列树）：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/1.jpg" alt="img" style="zoom: 25%;" />

只要从根遍历这棵树，记录路径上的数字，其实就是所有的全排列。**我们不妨把这棵树称为回溯算法的「决策树」**（或排列数）。

**为啥说这是决策树呢，因为你在每个节点上其实都在做决策**。比如说你站在下图的红色节点上：

<img src="https://labuladong.online/algo/images/backtracking/2.jpg" alt="img" style="zoom:25%;" />

你现在就在做决策，可以选择 1 那条树枝，也可以选择 3 那条树枝。为啥只能在 1 和 3 之中选择呢？因为 2 这个树枝在你身后，这个选择你之前做过了，而全排列是不允许重复使用数字的。

现在可以解答开头的几个名词：==`[2]` 就是「路径」，记录你已经做过的选择==；==`[1,3]` 就是「选择列表」，表示你当前可以做出的选择==；「结束条件」就是遍历到树的底层叶子节点，这里==也就是选择列表为空的时候==（条件）。

如果明白了这几个名词，可以把`「路径」和「选择」列表作为决策树上每个节点的属性`，比如下图列出了几个蓝色节点的属性：

<img src="https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/3.jpg" alt="img" style="zoom:33%;" />

我们定义的 `backtrack` 函数其实就像一个指针，在这棵树上游走，同时要==正确维护每个节点的属性==，每当走到树的底层叶子节点，其「路径」就是一个全排列。

再进一步，遍历这个决策树，并维护每个节点属性，最终得到答案「路径」

注：这里的每个节点的选择个数为 「选择」的个数，也就是本质上便是==遍历一个多叉树==，回忆一下多叉树的遍历框架

```python
class node:
    val: int
    childen: List[node]

def traverse():
    for i in node.childen:
        
        做选择
```



而「路径」和「选择」是每个节点的属性，函数在树上游走要正确处理节点的属性，那么就要在这两个特殊时间点搞点动作：

<img src="https://labuladong.online/algo/images/backtracking/5.jpg" alt="img" style="zoom:25%;" />

**我们只要在递归之前做出选择，在递归之后撤销刚才的选择**，就能正确得到每个节点的选择列表和路径。

全排列代码如下：

```java []
//java codes
class Solution {
    List<List<Integer>> res = new LinkedList<>();

    /* 主函数，输入一组不重复的数字，返回它们的全排列 */
    List<List<Integer>> permute(int[] nums) {
        // 记录「路径」
        LinkedList<Integer> track = new LinkedList<>();
        // 「路径」中的元素会被标记为 true，避免重复使用
        boolean[] used = new boolean[nums.length];
        
        backtrack(nums, track, used);
        return res;
    }

    // 路径：记录在 track 中
    // 选择列表：nums 中不存在于 track 的那些元素（used[i] 为 false）
    // 结束条件：nums 中的元素全都在 track 中出现
    void backtrack(int[] nums, LinkedList<Integer> track, boolean[] used) {
        // 触发结束条件
        if (track.size() == nums.length) {
            res.add(new LinkedList(track));
            return;
        }
        
        for (int i = 0; i < nums.length; i++) {
            // 排除不合法的选择
            if (used[i]) {
                // nums[i] 已经在 track 中，跳过
                continue;
            }
            // 做选择
            track.add(nums[i]);
            used[i] = true;
            // 进入下一层决策树
            backtrack(nums, track, used);
            // 取消选择
            track.removeLast();
            used[i] = false;
        }
    }
}

```
```python []
# python codes
from typing import List

class Solution:
    def __init__(self):
        self.res = []

    # 主函数，输入一组不重复的数字，返回它们的全排列
    def permute(self, nums: List[int]) -> List[List[int]]:
        # 记录「路径」
        track = []
        # 「路径」中的元素会被标记为 true，避免重复使用
        used = [False] * len(nums)
        
        self.backtrack(nums, track, used)
        return self.res

    # 路径：记录在 track 中
    # 选择列表：nums 中不存在于 track 的那些元素（used[i] 为 false）
    # 结束条件：nums 中的元素全都在 track 中出现
    def backtrack(self, nums: List[int], track: List[int], used: List[bool]):
        # 触发结束条件
        if len(track) == len(nums):
            self.res.append(track.copy())
            return
        
        for i in range(len(nums)):
            # 排除不合法的选择
            if used[i]: 

                # nums[i] 已经在 track 中，跳过
                continue
            # 做选择
            track.append(nums[i])
            used[i] = True
            # 进入下一层决策树
            self.backtrack(nums, track, used)
            # 取消选择
            track.pop()
            used[i] = False
```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

class Solution {
    private:
        vector<vector<int>> res;

        /* 主函数，输入一组不重复的数字，返回它们的全排列 */
        vector<vector<int>> permute(vector<int>& nums) {
            // 记录「路径」
            vector<int> track;
            //「路径」中的元素会被标记为true，避免重复使用
            vector<bool> used(nums.size(), false);

            backtrack(nums, track, used);
            return res;
        }

        // 路径：记录在 track 中
        // 选择列表：nums 中不存在于 track 的那些元素
        // 结束条件：nums 中的元素全都在 track 中出现
        void backtrack(vector<int>& nums, vector<int>& track, vector<bool>& used) {
            // 触发结束条件
            if (track.size() == nums.size()) {
                res.push_back(track);
                return;
            }

            for (int i = 0; i < nums.size(); i++) {
                // 排除不合法的选择
                if (used[i]) {
                    //nums[i] 已经在 track中，跳过
                    continue;
                }
                // 做选择
                track.push_back(nums[i]);
                used[i] = true;
                // 进入下一层决策树
                backtrack(nums, track, used);
                // 取消选择
                track.pop_back();
                used[i] = false;
            }
        }
    public:
        vector<vector<int>> permute(vector<int>& nums) {
            return permute(nums);
        }
};

```
```c []
// c codes
```

用回溯法解题的一个显著特征是在搜索过程中**动态产生问题的解空间**。在任何时刻，**算法只保存从根结点到当前扩展结点的路径**。



2、剪枝函数

回溯法搜索解空间树时，通常采用两种策略避免无效搜索，提高回溯法的搜索效率。常用的两种剪枝函数为 约束函数 和 限界函数 

一是用**约束函数**在扩展结点处剪去**不满足约束**的子树。

二是用**限界函数**剪去**得不到最优解**的子树

N 皇后问题和 0/1 背包问题正好是两种不同的类型，其中同时使用约束条件和目标函数的界进行裁剪的是 0/1 背包问题 ，只使用约束条件进行裁剪的是 N 皇后问题 。

3、回溯法的基本步骤

（1）针对所给问题，定义问题的解空间。

> > 生成问题状态的基本方法
>
> 1. 扩展结点（E-结点, Expansion Node）
>
>    一个**正在产生儿子的结点**称为扩展结点
>
> 2. 活结点（L-结点, Live Node）
>
>    一个**自身已生成但其儿子还没有全部生成**的节点称做活结点
>
> 3. 死结点（D-结点, Dead Node）
>
>    一个**所有儿子已经产生**的结点称做死结点
>
> > 深度优先的问题状态生成法
>
> 1. 如果对一个扩展结点R，一旦产生了它的一个儿子C，就把C当做新的扩展结点。
> 2. 在完成对子树C（以C为根的子树）的穷尽搜索之后，将R重新变成扩展结点，继续生成R的下一个儿子（如果存在）。
>
> > 宽度优先的问题状态生成法
>
> 1. 一个扩展结点变成死结点之前，它一直是扩展结点。

（2）确定易于搜索的解空间树。

（3）以深度优先方式搜索解空间，并在搜索过程中用剪枝函数避免无效搜索。

**空间复杂性 **& **时间复杂性**

> 用回溯法解题的一个显著特征是在搜索过程中动态产生问题的解空间。在任何时刻，算法只保存从根结点到当前扩展结点的路径。
> 如果解空间树中从根结点到叶结点的最长路径的长度为**h(n)**，则回溯法所需的计算空间通常为**O(h(n))**。
> 显式地存储整个解空间则需要O(2^h(n))或O(h(n)!)内存空间。
>
> ----
>
> 用回溯法设计解装载问题的O(2n)计算时间算法。
> 在某些情况下该算法优于动态规划算法。

 **子集树 & 排列树**

 ***子集树***：当所给的问题是**从n个元素的集合S中找出满足某种性质的子集**时，相应的解空间称为***子集树***。例如，那个物品的0-1背包问题所相应的解空间树就是一颗子集树。这类子集问题通常有2^n^ 个叶节点，其节点总个数为2^(n+1)-1^。遍历子集树的任何算法均需要O(2^n^)的计算时间。

![img](core%20algorithm.assets/051655557113181.jpg) 

***排列树***：当所给问题是确定**n个元素满足某种性质的排列**时，相应的解空间树称为***排列树***。排列树通常有n!个叶子节点。因此遍历排列树需要O(n!)的计算时间。
   ![img](core%20algorithm.assets/051658026801559.jpg)



##### 经典算法

画解空间树，0-1 背包的解空间树（满二叉树—子集树），货郎问题，程序作业问题（排列树）

###### 0-1 **背包的解空间树**

n=3，直接画一个满 2 叉树，除根节点 A，往下每一层表示物品 1—3，左 1 右 0，1 选 0 不选。下图在 L 节点取得最优值，则最优解为：011，即选择物品 2 和 3。(**子集树**)

<img src="core%20algorithm.assets/image-20231227191525809.png" alt="image-20231227191525809" style="zoom: 67%;" />

###### **旅行商问题 货郎担问题**

有n个城市，用1，2，…，n表示，城i,j之间的距离为dij，有一个货郎从城1出发到其他城市一次且仅一次，最后回到城市1，怎样选择行走路线使总路程最短？（注：该问题还可以用动态规划法求解）

> 每个城市走一遍，最后回到住地的路线，使总的路程最短。该问题是一个 NP 完全问题， 有(n-1)!条可选路线最优
>
> **排列树**
>
> 可以看到最后的结果中，解(1,3,2,4,1)有最优值 25 

<img src="core%20algorithm.assets/image-20231227192201625.png" alt="image-20231227192201625" style="zoom:67%;" />

###### **批处理作业调度**

批处理作业调度问题要从 n 个作业的所有排列中找出有最小完成时间和的作业调度，所以批处理作业调度问题的解空间是一颗排列树。

<img src="core%20algorithm.assets/image-20231227193459864.png" alt="image-20231227193459864" style="zoom: 67%;" />

##### N皇后问题

> 问题定义：在n×n的国际象棋棋盘上摆下n个皇后，使所有的皇后都不能攻击到对方，找出所有符合要求的情况。
>
> <img src="core%20algorithm.assets/queens.jpg" alt="img" style="zoom:50%;" />

分析：n后问题的解空间树是一棵排列树，**解与解之间不存在优劣的分别**（所以采用回溯而不是分支限定）。直到**搜索到叶结点时才能确定出一组解**。

采用回溯法可以系统地搜索问题的全部解。

![image-20231228083911777](core%20algorithm.assets/image-20231228083911777.png)

### Np问题

确定性问题版本的背包问题是NP的，

> 理解0-1背包问题的动态规划算法不是多项式时间算法。

P 是否等于 NP 是计算复杂度理论里面最著名的未解决的问题之一，一个 NP 完全问题，如果能找到解决它的多项式时间算法，那么就说明了 P = NP。

如今 0-1 背包问题已经被证明是 NP 完全问题，而它却有着一个动态规划解法，该解法有着 O(n*W) 的时间复杂度，其中 n 是物品的个数，W 是背包限制的最大负重。所以时间复杂度对输入 n，W 来说是多项式时间的，所以说明了 NP = P 是不是哪里出错了呢？

其实多项式时间是相对于输入规模来说的，输入规模最直观的理解就是输入到该算法的数据占了多少比特内存。0-1 背包的输入有 n 个物品的价值，n 个物品的重量，还有背包的最大负重 W。如今假设 W 占用的比特数为 L（也就是说背包的最大负重的输入规模是 L），那么 log(W) = L，所以 O(n*W) = O(n*2L)，由此看到，该算法的时间复杂度对于输入规模 L 来说是指数级别的，随着输入规模 L 的增加，运算时间会迅速增长。

实际上，人们把这种动态规划的算法称为伪多项式时间算法（pseudo-polynomial time algorithm），这种算法不能真正意义上实现多项式时间内解决问题。

## BFS系列算法

读完本文，你不仅学会了算法套路，还可以顺便解决如下题目：

|                           LeetCode                           |                             力扣                             | 难度 |
| :----------------------------------------------------------: | :----------------------------------------------------------: | :--: |
| [111. Minimum Depth of Binary Treeopen in new window](https://leetcode.com/problems/minimum-depth-of-binary-tree/) | [111. 二叉树的最小深度open in new window](https://leetcode.cn/problems/minimum-depth-of-binary-tree/) |  🟢   |
| [752. Open the Lockopen in new window](https://leetcode.com/problems/open-the-lock/) | [752. 打开转盘锁open in new window](https://leetcode.cn/problems/open-the-lock/) |  🟠   |
|                              -                               | [剑指 Offer II 109. 开密码锁open in new window](https://leetcode.cn/problems/zlDJc7/) |  🟠   |

BFS 的核心思想应该不难理解的，就是把一些问题抽象成图，从一个点开始，向四周开始扩散。一般来说，我们写 BFS 算法都是用「队列」这种数据结构，==每次将一个节点周围的所有节点加入队列==。

BFS 相对 DFS 的最主要的区别是：**BFS 找到的路径一定是最短的，但代价就是空间复杂度可能比 DFS 大很多**。

 BFS 出现的常见场景便是让你==在一幅「图」中找到从起点 `start` 到终点 `target` 的最近距离==，这个广义的描述可以有各种变体，比如走迷宫，有的格子是围墙不能走，从起点到终点的最短距离是多少？再比如说连连看游戏是如何判断它俩的最短连线有几个拐点的？

一幅「图」，让你从一个起点，走到终点，问最短路径。这就是 BFS 的本质，框架搞清楚了直接默写就好。

这里框架便是根据上文二叉树核心心法的层序遍历代码进一步优化出来的（重复访问的问题）：

```java []
//java codes
// 计算从起点 start 到终点 target 的最近距离
int BFS(Node start, Node target) {
    Queue<Node> q; // 核心数据结构
    Set<Node> visited; // 避免走回头路
    
    q.offer(start); // 将起点加入队列
    visited.add(start);

    while (q not empty) {
        int sz = q.size();
        /* 将当前队列中的所有节点向四周扩散 */
        for (int i = 0; i < sz; i++) {
            Node cur = q.poll();
            /* 划重点：这里判断是否到达终点 */
            if (cur is target)
                return step;
            /* 将 cur 的相邻节点加入队列 */
            for (Node x : cur.adj()) {
                if (x not in visited) {
                    q.offer(x);
                    visited.add(x);
                }
            }
        }
    }
    // 如果走到这里，说明在图中没有找到目标节点
}

```
```python []
# python codes
from typing import List, Set
from collections import deque

class Node:
    def __init__(self, val: int):
        self.val = val
        self.neighbors = []

def BFS(start: Node, target: Node) -> int:
    q = deque() # 核心数据结构
    visited = set() # 避免走回头路
    q.append(start) # 将起点加入队列
    visited.add(start)

    step = 0 # 记录扩散的步数

    while q:
        step += 1
        size = len(q)
        # 将当前队列中的所有节点向四周扩散
        for i in range(size):
            cur = q.popleft()
            # 划重点：这里判断是否到达终点
            if cur == target:
                return step
            # 将cur相邻节点加入队列
            for x in cur.neighbors:
                if x not in visited:
                    q.append(x)
                    visited.add(x)
    # 如果走到这里，说明在图中没有找到目标节点
    return -1

```
```c++ []
// c++ codes

int BFS(Node start, Node target) {
    queue<Node> q; 
    set<Node> visited;
    
    q.push(start); 
    visited.insert(start);

    while (!q.empty()) {
        int sz = q.size();
        for (int i = 0; i < sz; i++) {
            Node cur = q.front();
            q.pop();
            if (cur == target)
                return step;
            for (Node x : cur.adj()) {
                if (visited.count(x) == 0) {
                    q.push(x);
                    visited.insert(x);
                }
            }
        }
    }
    // 如果走到这里，说明在图中没有找到目标节点
}
```
```c []
// c codes
```

队列 `q` 就不说了，BFS 的核心数据结构；`cur.adj()` 泛指 `cur` 相邻的节点，比如说二维数组中，`cur` 上下左右四面的位置就是相邻节点；`visited` 的主要作用是防止走回头路，大部分时候都是必须的，但是像一般的二叉树结构，没有子节点到父节点的指针，不会走回头路就不需要 `visited`，如上文的层序遍历代码。

## DFS系列算法

 [以树的视角看动归/回溯/DFS算法的区别和联系](https://labuladong.online/algo/essential-technique/binary-tree-summary-2/#以树的视角看动归-回溯-dfs算法的区别和联系)

前文我说动态规划/回溯算法就是二叉树算法两种不同思路的表现形式，相信能看到这里的读者应该也认可了我这个观点。但有细心的读者经常问我：东哥，你的理解思路让我豁然开朗，但你好像一直没讲过 DFS 算法？

其实我在 [一文秒杀所有岛屿题目](https://labuladong.online/algo/frequency-interview/island-dfs-summary/) 中就是用的 DFS 算法，但我确实没有单独用一篇文章讲 DFS 算法，**因为 DFS 算法和回溯算法非常类似，只是在细节上有所区别**。

这个细节上的差别是什么呢？其实就是「做选择」和「撤销选择」到底在 for 循环外面还是里面的区别，DFS 算法在外面，回溯算法在里面。

为什么有这个区别？还是要结合着二叉树理解。这一部分我就把回溯算法、DFS 算法、动态规划三种经典的算法思想，以及它们和二叉树算法的联系和区别，用一句话来说明：

**动归/DFS/回溯算法都可以看做二叉树问题的扩展，只是它们的关注点不同**：

- **动态规划算法属于分解问题的思路，它的关注点在整棵「子树」**。
- **回溯算法属于遍历的思路，它的关注点在节点间的「树枝」**。
- **DFS 算法属于遍历的思路，它的关注点在单个「节点」**。

怎么理解？我分别举三个例子你就懂了：

**第一个例子**，给你一棵二叉树，请你用分解问题的思路写一个 `count` 函数，计算这棵二叉树共有多少个节点。代码很简单，上文都写过了：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

//定义:输入一棵二叉树，返回这棵二叉树的节点总数
int count(TreeNode* root) {
    if (root == NULL) {
        return 0;
    }
    //我这个节点关心的是我的两个子树的节点总数分别是多少
    int leftCount = count(root->left);
    int rightCount = count(root->right);
    //后序位置，左右子树节点数加上自己就是整棵树的节点数
    return leftCount + rightCount + 1;
}
```

**你看，这就是动态规划分解问题的思路，它的着眼点永远是结构相同的整个子问题，类比到二叉树上就是「子树」**。

你再看看具体的动态规划问题，比如 [动态规划框架套路详解](https://labuladong.online/algo/essential-technique/dynamic-programming-framework/) 中举的斐波那契的例子，我们的关注点在一棵棵子树的返回值上：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

int fib(int N) {
    if (N == 1 || N == 2) return 1;
    return fib(N - 1) + fib(N - 2);
}
```

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/2.jpg)

**第二个例子**，给你一棵二叉树，请你用遍历的思路写一个 `traverse` 函数，打印出遍历这棵二叉树的过程，你看下代码：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

void traverse(TreeNode* root) {
    if (root == nullptr) return;
    printf("从节点 %s 进入节点 %s", root, root->left);
    traverse(root->left);
    printf("从节点 %s 回到节点 %s", root->left, root);

    printf("从节点 %s 进入节点 %s", root, root->right);
    traverse(root->right);
    printf("从节点 %s 回到节点 %s", root->right, root);
}
```

不难理解吧，好的，我们现在从二叉树进阶成多叉树，代码也是类似的：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

// 多叉树节点
class Node {
public:
    int val;
    vector<Node*> children;
};

void traverse(Node* root) {
    if (root == nullptr) return;
    for (Node* child : root->children) {
        printf("从节点 %s 进入节点 %s", root, child);
        traverse(child);
        printf("从节点 %s 回到节点 %s", child, root);
    }
}
```

这个多叉树的遍历框架就可以延伸出 [回溯算法框架套路详解](https://labuladong.online/algo/essential-technique/backtrack-framework/) 中的回溯算法框架：



```java
void backtrack(...) {
    for (int i = 0; i < ...; i++) {
        // 做选择
        ...

        // 进入下一层决策树
        backtrack(...);

        // 撤销刚才做的选择
        ...
    }
}
```

**你看，这就是回溯算法遍历的思路，它的着眼点永远是在节点之间移动的过程，类比到二叉树上就是「树枝」**。

你再看看具体的回溯算法问题，比如 [回溯算法秒杀排列组合子集的九种题型](https://labuladong.online/algo/essential-technique/permutation-combination-subset-all-in-one/) 中讲到的全排列，我们的关注点在一条条树枝上：

```java
// 回溯算法核心部分代码
void backtrack(int[] nums) {
    // 回溯算法框架
    for (int i = 0; i < nums.length; i++) {
        // 做选择
        used[i] = true;
        track.addLast(nums[i]);

        // 进入下一层回溯树
        backtrack(nums);

        // 取消选择
        track.removeLast();
        used[i] = false;
    }
}
```

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/2.jpeg)

**第三个例子**，我给你一棵二叉树，请你写一个 `traverse` 函数，把这棵二叉树上的每个节点的值都加一。很简单吧，代码如下：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖



```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

void traverse(TreeNode* root) {
    if (root == nullptr) return;
    // 遍历过的每个节点的值加一
    root->val++;
    traverse(root->left);
    traverse(root->right);
}
```

**你看，这就是 DFS 算法遍历的思路，它的着眼点永远是在单一的节点上，类比到二叉树上就是处理每个「节点」**。

你再看看具体的 DFS 算法问题，比如 [一文秒杀所有岛屿题目](https://labuladong.online/algo/frequency-interview/island-dfs-summary/) 中讲的前几道题，我们的关注点是 `grid` 数组的每个格子（节点），我们要对遍历过的格子进行一些处理，所以我说是用 DFS 算法解决这几道题的：



```java
// DFS 算法核心逻辑
void dfs(int[][] grid, int i, int j) {
    int m = grid.length, n = grid[0].length;
    if (i < 0 || j < 0 || i >= m || j >= n) {
        return;
    }
    if (grid[i][j] == 0) {
        return;
    }
    // 遍历过的每个格子标记为 0
    grid[i][j] = 0;
    dfs(grid, i + 1, j);
    dfs(grid, i, j + 1);
    dfs(grid, i - 1, j);
    dfs(grid, i, j - 1);
}
```

![img](https://markdown-1311598839.cos.ap-nanjing.myqcloud.com/5.jpg)

好，请你仔细品一下上面三个简单的例子，是不是像我说的：动态规划关注整棵「子树」，回溯算法关注节点间的「树枝」，DFS 算法关注单个「节点」。

有了这些铺垫，你就很容易理解为什么回溯算法和 DFS 算法代码中「做选择」和「撤销选择」的位置不同了，看下面两段代码：

java 🟢cpp 🤖python 🤖go 🤖javascript 🤖

```cpp
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

// DFS 算法把「做选择」「撤销选择」的逻辑放在 for 循环外面
void dfs(Node* root) {
    if (root == NULL) return;
    // 做选择
    printf("我已经进入节点 %p 啦\n", root);
    for (Node* child : root->children) {
        dfs(child);
    }
    // 撤销选择
    printf("我将要离开节点 %p 啦\n", root);
}

// 回溯算法把「做选择」「撤销选择」的逻辑放在 for 循环里面
void backtrack(Node* root) {
    if (root == NULL) return;
    for (Node* child : root->children) {
        // 做选择
        printf("我站在节点 %p 到节点 %p 的树枝上\n", root, child);
        backtrack(child);
        // 撤销选择
        printf("我将要离开节点 %p 到节点 %p 的树枝上\n", child, root);
    }
}
```

看到了吧，你回溯算法必须把「做选择」和「撤销选择」的逻辑放在 for 循环里面，否则怎么拿到「树枝」的两个端点？

## 图论

**更进一步，图论相关的算法也是二叉树算法的延续**。

比如 [图论基础](https://labuladong.online/algo/data-structure/graph-traverse/)，[环判断和拓扑排序](https://labuladong.online/algo/data-structure/topological-sort/) 和 [二分图判定算法](https://labuladong.online/algo/data-structure/bipartite-graph/) 就用到了 DFS 算法；再比如 [Dijkstra 算法模板](https://labuladong.online/algo/data-structure/dijkstra/)，就是改造版 BFS 算法加上一个类似 dp table 的数组。

## 排序系列算法

###  [快速排序](https://labuladong.online/algo/practice-in-action/quick-sort/)

**快速排序就是个二叉树的前序遍历**

快速排序的逻辑是，若要对 `nums[lo..hi]` 进行排序，我们先找一个分界点 `p`，通过交换元素使得 `nums[lo..p-1]` 都小于等于 `nums[p]`，且 `nums[p+1..hi]` 都大于 `nums[p]`，然后递归地去 `nums[lo..p-1]` 和 `nums[p+1..hi]` 中寻找新的分界点，最后整个数组就被排序了。

快速排序的代码框架如下：

```java []
//java codes
void sort(int[] nums, int lo, int hi) {
    /****** 前序遍历位置 ******/
    // 通过交换元素构建分界点 p
    int p = partition(nums, lo, hi);
    /************************/

    sort(nums, lo, p - 1);
    sort(nums, p + 1, hi);
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

def sort(nums: List[int], lo: int, hi: int):
    # 前序遍历位置
    # 通过交换元素构建分界点 p
    p = partition(nums, lo, hi)
    sort(nums, lo, p - 1)
    sort(nums, p + 1, hi)

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

void sort(int nums[], int lo, int hi) {
    /****** 前序遍历位置 ******/
    // 通过交换元素构建分界点 p
    int p = partition(nums, lo, hi);
    /************************/

    sort(nums, lo, p - 1);
    sort(nums, p + 1, hi);
}

```
```c []
// c codes
```

先构造分界点，然后去左右子数组构造分界点，你看这不就是一个二叉树的前序遍历吗？

### 归并排序

归并排序的逻辑，若要对 `nums[lo..hi]` 进行排序，我们先对 `nums[lo..mid]` 排序，再对 `nums[mid+1..hi]` 排序，最后把这两个有序的子数组合并，整个数组就排好序了。

归并排序的代码框架如下：

```java []
//java codes
// 定义：排序 nums[lo..hi]
void sort(int[] nums, int lo, int hi) {
    int mid = (lo + hi) / 2;
    // 排序 nums[lo..mid]
    sort(nums, lo, mid);
    // 排序 nums[mid+1..hi]
    sort(nums, mid + 1, hi);

    /****** 后序位置 ******/
    // 合并 nums[lo..mid] 和 nums[mid+1..hi]
    merge(nums, lo, mid, hi);
    /*********************/
}

```
```python []
# python codes
# 注意：python 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
# 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

# 定义：排序 nums[lo..hi]
def sort(nums: List[int], lo: int, hi: int):
    mid = (lo + hi) // 2
    # 排序 nums[lo..mid]
    sort(nums, lo, mid)
    # 排序 nums[mid+1..hi]
    sort(nums, mid + 1, hi)

    ######### 后序位置 #########
    # 合并 nums[lo..mid] 和 nums[mid+1..hi]
    merge(nums, lo, mid, hi)
    ###########################

```
```c++ []
// c++ codes
// 注意：cpp 代码由 chatGPT🤖 根据我的 java 代码翻译，旨在帮助不同背景的读者理解算法逻辑。
// 本代码不保证正确性，仅供参考。如有疑惑，可以参照我写的 java 代码对比查看。

// 定义：排序 nums[lo..hi]
void sort(vector<int>& nums, int lo, int hi) {
    int mid = (lo + hi) / 2;
    // 对 nums[lo..mid] 进行排序
    sort(nums, lo, mid);
    // 对 nums[mid+1..hi] 进行排序
    sort(nums, mid + 1, hi);

    /****** 在后序位置进行归并操作 ******/
    // 合并 nums[lo..mid] 和 nums[mid+1..hi]
    merge(nums, lo, mid, hi);
    /**********************************/
}

```
```c []
// c codes
```

先对左右子数组排序，然后合并（类似合并有序链表的逻辑），你看这是不是二叉树的后序遍历框架？另外，这不就是传说中的分治算法嘛，不过如此呀。

如果你一眼就识破这些排序算法的底细，还需要背这些经典算法吗？不需要。你可以手到擒来，从二叉树遍历框架就能扩展出算法了。

说了这么多，旨在说明，二叉树的算法思想的运用广泛，甚至可以说，只要涉及递归，都可以抽象成二叉树的问题。

## 分支限定法

回溯和分支限界法是比较常用的对候选解进行系统检查两种方法。按照这两种方法对候选解进行系统检查通常会使问题的求解时间大大减少（无论对于最坏情形还是对于一般情形） 。可以避免对**很大的候选解集合进**行检查，同时能够保证算法运行结束时可以找到所需要的解。通常能够用来求解规模很大的问题。

回溯法（Backtracking）和分支限定法（Branch and Bound）是解决决策问题和优化问题的两种算法策略，它们在某些方面有相似之处，但也有明显的区别：

### 回溯法（Backtracking）
1. **定义**：回溯法是一种通过试错的方式尝试分步解决问题的算法。它在遇到当前问题的一个解的候选时，会尝试将其加入解中，并继续搜索下去。如果发现这个选择会导致一个不可能的解（即死路），算法会回溯到上一步，撤销那个选择，并尝试其他的选择。
2. **应用场景**：回溯法常用于解决组合问题、排列问题、划分问题等，例如八皇后问题、图的着色问题、旅行商问题（TSP）等。
3. **特点**：
   - 通过递归或迭代实现。
   - 需要剪枝操作来减少搜索空间，避免不必要的搜索。
   - 不一定能找到最优解，除非搜索完整个解空间。

### 分支限定法（Branch and Bound）
1. **定义**：分支限定法是一种在搜索解空间时使用界限来排除不可能成为最优解的分支的算法。它结合了分支（分治搜索）和限定（确定界限）两种策略，通过上下界估计来剪枝，从而减少搜索空间。
2. **应用场景**：分支限定法通常用于求解优化问题，特别是那些具有明确目标函数的组合优化问题，如最短路径问题、最大团问题等。
3. **特点**：
   - 需要一个目标函数来评估解的质量。
   - 使用界限（通常是目标函数的上界和下界）来指导搜索。
   - 保证能找到最优解，如果算法设计得当。

### 区别
1. **目标**：回溯法主要用于找到所有可能的解或满足条件的解，而分支限定法主要用于找到最优解。
2. **剪枝**：回溯法通过剪枝减少搜索空间，但不一定能找到最优解；分支限定法通过界限来剪枝，保证能找到最优解。
3. **解的评估**：回溯法不需要评估解的质量，只关心解的合法性；分支限定法则需要评估解的质量，以确定是否继续搜索某个分支。
4. **算法效率**：分支限定法通常比回溯法更高效，因为它通过界限来减少不必要的搜索。

总的来说，回溯法和分支限定法都是解决组合问题的有效方法，但它们在目标、剪枝策略和解的评估方面存在明显差异。分支限定法通常用于优化问题，而回溯法则更适用于解空间的搜索问题。

#### 分支限定法

回溯法以深度优先的方式搜索解空间树，而分支限界法则以**广度优先或以最小耗费优先的方式**搜索解空间树。分支限界法中如果某孩子结点的目标函数可能取得的值超出目标函数的界，则将其丢弃，因为从这个结点生成的解不会比目前已经得到的解更好；否则，将其加入待处理结点表。该方法通过限界函数剪枝操作很好的减少了搜索数量次数，

下表列出了回溯法和分支限界法的一些区别：

| **方法**   | **对解空间树的搜索方式**   | **存储结点的常用数据结构** | **结点存储特性**                             | **常用应用**                                 |
| ---------- | -------------------------- | -------------------------- | -------------------------------------------- | -------------------------------------------- |
| 回溯法     | 深度优先搜索               | 栈                         | 活结点的所有可行子结点被遍历后才被从栈中弹出 | 找出满足约束条件的所有解                     |
| 分支限界法 | 广度优先或最小消耗优先搜索 | 队列、优先队列             | 每个结点只有一次成为扩展结点的机会           | 找出满足约束条件的一个解或特定意义下的最优解 |

> 在分支限界法中，每一个活结点只有一次机会成为扩展结点。
> 活结点一旦成为扩展结点，就一次性产生其所有儿子结点。**在这些儿子结点中，导致不可行解或导致非最优解的儿子结点被舍弃，其余儿子结点被加入活结点表中。**
> 从活结点表中取下一结点成为当前扩展结点，并重复上述结点扩展过程
> 这个过程一直持续到找到所求的解或活结点表为空时为止。

从活结点表中选择下一扩展结点的不同方式导致不同的分支限界法，常见的分支限界法分为:

1. 队列式分支限界法: 将活结点表组织成一个**队列**，并按照队列先进先出(FIFO) 原则选取下一个结点为扩展结点
2. 优先队列式分支限界法: 将活结点表组织成一个**优先队列 (用堆实现)**并选取**优先级最高**的活结点成为当前扩展结点。

##### 经典算法

有一批共n个集装箱要装上2艘载重量分别为C1和C2的轮船，其中集
装箱i的重量为Wi，且<img src="core%20algorithm.assets/image-20231228084135364.png" alt="image-20231228084135364" style="zoom: 33%;" />

装载问题要求确定是否有一个合理的装载方案可将这个集装箱装上这2艘轮船。如果有，找出一种装载方案。 
容易证明：如果一个给定装载问题有解，则采用下面的策略可得到最优装载方案。 
(1)首先将第一艘轮船尽可能装满；
(2)将剩余的集装箱装上第二艘轮船。 

不难看出，右边的左边为1即为装，只要叶子节点时剩余大于第二艘船即可



<img src="core%20algorithm.assets/image-20231229181750293.png" alt="image-20231229181750293" style="zoom:67%;" />

<img src="core%20algorithm.assets/image-20231228084554293.png" alt="image-20231228084554293" style="zoom:67%;" />

参考文章：

https://cloud.tencent.com/developer/article/1582245

https://blog.csdn.net/weixin_41387874/article/details/120052490

https://www.freecodecamp.org/chinese/news/dijkstras-shortest-path-algorithm-visual-introduction/
