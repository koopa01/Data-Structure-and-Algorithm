# 第一章 数据结构
## 基本概念和术语
    1.数据：描述客观事物的符号，是计算机中可以操作的对象，是能被计算机事别（可传入计算机中），并输入给计算机处理的符号集合。
        包括整型、实型、字符、声音、图像等非数值型
    2.数据元素：是组成数据的、有一定意义的基本单位，在计算机中通常作为整体处理。也被称为记录。
        在人类中，人就是数据元素
    3.数据项：一个数据元素可以有若干个数据项组成。
        人这个数据元素中，有眼、耳、鼻等数据项，也可以有年龄、姓名、出生地址等数据项。
        数据项是不可分割的最小单位。（真正讨论问题时，数据元素才是数据结构中建立数据模型的着眼点）
    4.数据对象：是性质相同的数据元素的集合，是数据的子集。
        性质相同：指数据元素具有相同数量和类型的数据项，比如：人都有姓名、生日、性别等数据项。
        处理的数据元素通常具有相同性质，为避免混淆，将数据对象都简称为数据。
    5.数据结构：是相互之间存在一种或多种特定关系的数据元素的集合。
        不同数据元素之间不是独立的，而是存在特定的关系，将这些关系称之为结构。

## 逻辑结构与物理结构
    一、逻辑结构：指数据对象中数据元素之间的相互关系。
        1.集合结构：集合结构中的数据元素除了同属于一个集合外，他们之间没有其他关系。
            即：个数据元素是‘平等’的，他们的共同属性是‘同属于一个集合’。
        2.线性结构：线性结构中的数据元素之前是一对一的关系。
        3.树形结构：树形结构中的数据元素之前存在一种一对多的层次关系。
        4.图形结构：图形结构的数据元素是多对多的关系。
    二、物理结构：指数据的逻辑结构在计算机中的存储形式。
        1.顺序存储结构：是把数据元素存放在地址连续的存储单元里，其数据间的逻辑关系和物理关系是一致的。
            就是排队展位，按顺序排好，没人占一小段空间，谁也别插队。（数组）
        2.链式存储结构：把数据元素存放在任意的存储单元里，这组存储单元可以是连续的，也可以是不连续的。
            需要用指针存放数据元素的地址，通过地址找到相关联数据元素的位置。
    逻辑结构是面向问题的，物理结构是面向计算机的，其基本目标即是将数据及其逻辑关系存储到计算机中。
## 抽象数据类型
    1.数据类型：指一组性质相同的值的集合及定义在刺激和尚的一些操作的总称。
        数据需要分配内存，内存是有限的，就需要对数据分类，分出多种类型以便控制内存大小。
        原子类型：不可分解的基本类型，比如：整形、实型、字符型等。
        结构类型：有若干个类型组合而成，是可以再分解的，比如：整型数组
    2.抽象数据类型(ADT)：指一个数学模型及定义在该模型上的一组操作。
        抽象：指抽取出事物具有的普遍性的性质。
        抽象的意义在于数据类型的数学抽象特性。
        抽象数据类型的定义仅取决于他的一组逻辑特性，而与其在计算机内部如何表示和实现无关。
            抽象数据类型体现了程序设计中问题分解、抽象和信息隐藏的特性。
## 小结
    |                      数据                                      |
    |                     数据对象                                    |
    |     数据元素        |     数据元素         |    数据元素         |
    |数据项1  |  数据项2  |  数据项3  |  数据项4  |  数据项5  |  数据项6|

# 第二章 算法
    算法：是解决特定问题求解步骤的描述，在计算机中表现为指令的有限序列，并且每个指令表示一个或多个操作。
## 算法的特性
    算法可以帮助更好的理解数据结构
    1.输入输出：零个或多个输入，至少一个或多个输出
    2.有穷性：执行有限的步骤后可以自动结束（每个步骤在可接受的时间内完成）
    3.确定性：算法每一步有确定的含义，不会有二义性
    4.可行性：算法每一步都必须可行（每一步可以通过执行有限次数完成）
## 算法设计要求（标准）
    1.正确性
        1.没有语法错误
        2.对合法的输入数据产生满足要求的输出结果
        * 3.对非法的输入数据产生满足规格说明的结果
        4.对精心选择甚至刁难的测试数据都有满足要求的输出结果
    2.可读性
        便于阅读、理解和交流
    3.健壮性
        当输入数据不合法时，算法能做出相应的处理，而不是异常或是莫名其妙的结果
    4.时间效率高，存储量低
## 算法效率的度量方法
    1.事后统计法
        通过设计好的测试程序和数据，利用计算机计时器对不同算法编制的程序的运行时间进行比较，从而确定效率高低
            1.必须事前编写测试程序
            2.依赖硬件软件等环境因素
            3.测试数据的规模设计困难
        综上，缺陷很大，不予考虑。
    2.事前估计法
        在程序编制前，依据统计方法对算法进行估算
        影响效率的因素：
            1.算法采用的策略、方法（根本）
            2.编译产生的代码质量
            3.问题的输入规模（根本）
            4.机器执行指令的速度
## 算法的时间复杂度
    从小到大：
    O(c) < O(logn) < O(n) < O(n*logn) < O(n^2) < O(n^3) < O(2^n) < O(n!) < O(n^n)
    推导方法：
        1.没有加法常数不考虑
        2.只保留最高阶项
        3.去除与这项相乘的常数
    所提到的运行时间都是最坏情况下的运行时间
    平均运行时间是期望的结果，最有意义
## 算法的空间复杂度
    算法最好用空间换时间
    空间复杂度 S(n) = O(f(n))
        n为问题规模
        f(n)为语句关于n所占存储空间的函数

# 第三章 线性表(List)
**核心就是“工作指针后移”**
    零个或多个数据元素的有限序列（排好队的组织方式，知道前一个是谁，后一个是谁）
        1.是序列，有顺序，有限的，有头有尾。
        2.当仅有0个元素时，为空表。
        3.在复杂的线性表中，一个数据元素可以由多个数据项组成
        4.数据之间是一对一的关系

## 线性表的顺序存储结构
    1.指的是用一段地址连续的存储单元一次存储线性表的数据元素
        可用一维数组实现顺序存储结构
    2.顺序存储结构需要三个特性：
        1.存储空间的起始位置：数组data的存储位置
        2.线性表的最大存储容量：数组长度Maxsize
        3.线性表的当前长度：length
    3.数组的长度是存放线性表的存储空间的长度，时不变的。
        线性表的长度是线性表中数据元素的个数，随插入、删除而变化。
    4.任意时刻，线性表长度应 < 数组的长度
    5.地址计算方法：存储器中的每个存储单元都有自己的编号，称为地址
        Location(Ai+1) = Location(A) + c
        Location(Ai) = Location(a1) + (i-1)*c
    6.算出线性表中的任意位置的时间都是相同的（任意位置存取数据时间都相同且为常数）
        存储性能 —— 时间复杂度O(1)
        也成为随机存取结构

## 顺序存储结构的插入与删除
    线性表的顺序存储结构，在存、读数据时，不管哪个位置时间复杂度都是O(1)
        在插入、删除时，时间复杂度都是O(n)
    优点：1.无需为表中元素之间的逻辑关系而增加额外存储空间
        2.可以快速的存取表中任意位置的元素
    缺点：1.插入和删除操作需要移动大量元素
        2.当线性表长度变化较大时，难以确定存储空间的容量
        3.造成存储空间的“碎片”

## 线性表的链式存储结构
    既然插入删除时会造成存储空间“碎片”，那就让所有元素不要考虑相邻的位置，哪有空位就到哪里，前一个元素跟后一个元素的内存地址相连
    数据元素信息 + 直接后继元素的存储地址 ——>可以存储在内存未被占用的任意位置
        数据域   +      指针域（存储的指针/链）   ——>两部分信息组成数据的存储映像，称为节点(Node)
    链表的每个节点中只包含一个指针域，叫做单链表
        链表第一个节点的存储位置叫头指针，最后一个节点的指针为“空”（Null 或 “ ^ ”）
        单链表的第一个节点前附设一个节点，叫头节点，可以不存储任何信息，也可以存储线性表长度等附加信息，指针域存储指向第一个节点的指针

## 单链表的读取
    对单链表实现获取第i个元素的数据的操作GetElem：
        1.声明一个节点p指向链表第一个节点，初始化j从1开始
        2.当j < i时，遍历链表，让p的指针向后移动，不断指向下一个节点，j累加1
        3.若链表末尾p为空，则说明第i个元素不存在
        4.否则查找成功，返回节点p的数据
            就是从头开始找，直到第i个元素位置。当i = n时，遍历n - 1次，因此最坏情况时间复杂度O(n)

## 单链表的插入与删除
    1.插入
        ——> a1 | a1 ——> a2 | a2 ——>
               p       p ——> next
        让 e | e = s 插入a1和a2
        只需改变s ——> next = p ——> next,之后 p ——> next = s
        即，让p的后继节点改成s的后继节点，再把节点s变成p的后继节点
            如果先 p ——> next = s, 再s ——> next = p ——> next则会造成先覆盖了s的地址，后一步为s指向s的存储地址。
    2.删除
        设a2的节点为q，要实现将节点q删除单链表
            就是将它的前继节点的指针绕过，指向它的后继节点即可。
        ——> a1 | a1 ——> a2 | a2 ——> a3 | a3  ——>
               p     q/p ——> next   q ——> next
        只需p ——> next = p ——> next ——> next，或者 q = p ——> next; p ——> next = q ——> next
    3.总结
        插入和删除都是由两部分组成：
            1.遍历查找第i个元素
            2.插入或删除元素
        时间复杂度都是O(n)，即不管一次插入多少元素，删除多少元素，只需遍历一次。这就是单链表的效率优势。

## 单链表的整表创建
    其实就是一个数组的初始化，但电表可以很散，不像顺序存储结构这么集中，是动态结构，所占空间大小和位置不需预先分配划定。
        创建的算法（就是插入操作）：
            1.声明一节点p和计数器变量i
            2.初始化一空链表L
            3.让L的头节点的指针指向NULL，即建立一个带头结点的单链表
            4.循环：
                + 生成一新结点赋值给p
                + 随机生成艺术字赋值给p的数据域 p ——> data
                + 将p插入到头节点与前一新节点之间
                + 最后 pn ——> next = NULL
        实际应用可以采用尾插法，即每次把新结点插入到终端节点的后面。

## 单链表的整表删除
    注意：一定要声明前后两个变量p、q，因为p既有数据域，还有指针域，始放p实际是对他整个节点进行删除和内存释放，需要等当前节点释放后，把下一节点拿回来补充，否则会报错。
        1.声明一节点p和q
        2.将第一个节点赋值给p
        3.循环：
            + 将下一节点赋值给q
            + 释放p
            + 将q赋值给p

## 单链表 和 顺序存储 的结构优缺点
    存储分配方式：
        1.顺序存储用连续的存储单元，连续存储
        2.单链表用任意存储单元，实现链式存储
    时间性能：
        查找：
            1.顺序存储 O(1)
            2.单链表 O(n)
        插入和删除：
            1.顺序存储需平均一共表长一半的元素，O(n)
            2.单链表只需更改某一或两个指针，O(1)
    空间性能：
        1.顺序存储需预分配存储空间，分大浪费，分小溢出
        2.单链表任意分配存储空间，元素个数不受限制
    结论:
        1.需频繁查找用顺序存储，比如用户注册的个人信息，插入一次之后都是读取
        2.需频繁插入删除用单链表，比如游戏装备列表，随时增加删除
        3.当元素个数变化较大或未知多大时，用线性表
        4.当事先知道大致长度，用顺序存储，比如时间（只有12个月，一周七天）

## 静态链表
    不用指针，用数组代替指针实现的单链表，即用数组表述的链表叫做静态链表
    用游标实现法：
        1.用data数据域和cur数据域表示
        2.先对数组第一个和最后一个元素做特殊元素处理，不存数据
        3.首元素的data不存数据，cur存备用链表（闲置的节点）的第一个节点下标
        4.最后一个元素的data不存数据，cur用来存放第一个插入元素的小标，相当于头节点
## 循环链表
    将单链表中终端节点的之诊断有空指针改为指向头节点，使整个单链表形成一个环，即头尾相接。
    可从一个结点出发，访问到整个链表的所有节点
        1.和单链表相似，只是最后的节点指向头节点
        2.改变循环的判断条件，原来是判断 p ——> next, 现在是 p ——> next 不等于头节点，则循环未结束。
    这样先有头节点，需要循环整个链表才能找到终端节点
        如果不用头指针，用尾指针则可最快找到头节点和终端节点
    合并的时候，假设两个尾指针的循环链表，只需终端节点A指向终端节点B的下一个元素，终端节点B指向终端节点A的下一个元素

## 双向链表
    单链表中，查找下一个元素用next指针，时间复杂度O(1),查找上一个节点最坏就是O(n)
        双向链表实在单链表的每个节点中都有两个指针域，一个指向直接后续，另一个指向直接前驱。即用空间换时间
    双向链表可以反向遍历查找，但是插入和删除需要更改两个指针变量
    插入操作需：
        先把目标节点的两个指针分别给前节点的后指针和后节点的前指针
        再把前节点的后指针和厚街店的前指针指向目标节点
    删除操作同理
## 总结
                    线性表
    顺序存储结构 | 链式存储结构
                | 单链表 | 静态链表 | 循环链表 | 双向链表

# 第四章 栈与队列
    栈使限定在表尾进行插入和删除操作的线性表
    队列是只允许在一端进行插入操作、而在另一端进行删除操作的线性表
    栈的插入：进栈、压栈、入栈 push()
    栈的删除：出栈、弹栈 pop()
    如果元素数量多，出栈的变化将会更多，例如：1进，2进，2出，1出，3进，3出——2，1，3
## 栈的顺序存储结构及实现
    栈是线性表的特例：线性表顺序存储的简化 —— 顺序栈
    先进后出，数组的0为栈底。
    top变量为指示栈顶元素在数组中的位置，空栈top = -1
    存储栈的长度为StackSize > top
    进栈push，出栈pop
## 两栈共享空间
    相同数据类型的栈可以共享存储空间，数组有两个端点，两栈有两个栈底，让一个栈的栈底为数组的始端(0)，另一个栈为栈的末端(n-1)，这样两个栈增加元素就是两端点向中间延申    
    通常这样的数据结构需要两栈的空间需求有相反关系，不会都共同增长
## 栈的链式存储结构及实现
    简称为链栈
    单链表有头指针，栈有栈顶指针，可以合二为一。
    栈顶在单链表的头部，链栈不需要头节点。空的链栈是top = NULL
    进栈push：链表最开头插入新元素，之前的栈顶元素付给新结点的直接后继，top指针从之前的第一个元素指向现在的第一个元素（插入的新元素）
    出栈pop：将栈顶指针下移一位，释放顶部元素。
## 队列
    只允许在一段进行插入，而在另一端进行删除操作的线性表（先进先出）
    栈和队列都是特殊的线性表，只不过对插入删除做出了限制。都有顺序存储和链式存储方式
    链式存储结构不需要担心由于队列长度需要面临数组溢出的问题。

## 总结
    栈：顺序栈，两栈共享空间
        链栈
    队列：顺序队列，循环队列——避免数组插入和删除是需要移动数据，使队头队尾可以在数组中循环变化
        链队列

# 串
    串(string)由零个或多个字符组成的有限序列，又叫字符串
    串可以比较大小，比较的是相同位置索引的字母表顺序 "ab" < "ac"，也是字符之间的ASCII编码大小
        ASCII码由8位2进制数表示一个字符，共可表示256个字符，但只能表示英语字母和特殊符号。
        后由Unicode编码，由16位的2进制数表示一个字符，共可表示216个字符，约65万多个字符。
        前256个字符与ASCII码完全相同所以兼容。
## 串的抽象数据类型
    串的逻辑结构和线性表相似，但是串的基本操作与线性表有很大不同，线性表更关注单个元素的查找、插入、删除，串中更多的是查找子串、得到指定位置字串、替换字串。
    串是用一组地址连续的存储单元来存储串中的字符排列，即顺序存储结构，一般按照预定义大小分配定长数组。
        一般可以将实际的串长度值保存在数组0下标的位置
        对于串的顺序存储可在程序执行过程中动态分配得出
    若串采用链式存储，每个元素是一个字符或多个字符，结尾用“#”或 非串值字符不全。
        除了在串与串之间操作时有一定方便，其他情况不如顺序存储灵活，性能不如顺序存储好。
## 朴素模式匹配算法
    字串的定位操作通常称作串的模式匹配，比如定位单词在文章中位置来统计的出现频率
    对主串的每一个字符作为字串的开头，与要匹配的字符串进行匹配。对主串做大循环，对主串的每一个字符做子串长度的小循环，直到匹配成功或遍历为止。
        最好情况，一开始就匹配成功，O(1)
        稍差情况，之前都匹配不成功，最后匹配成功/不成功，一直不用遍历字串，O(n+m)，n为主串长度，m为字串长度，平均是(n+m)/2，即O(n+m)
        最差情况，每次不成功都在子串的最后一个字符，O((n-m+1)*m)
    此方法太低效
## KMP模式匹配算法
    克努特-莫里斯-普拉特算法 —— KMP算法 —— 尽量减少回溯来省略步骤
    假设主串S = "abcdefg"，字串T = "abcdex"
        1.S与T比较首字母、第二字母、……直到最后一个字母，"f"与"x"不相等。
        2.S的第二个字母"b"与T比较
        ……
        6.S的第六个字母"e"与T比较
*也就是说，如果直到T串中首字符"a"与T中后面的字符均不相等，T中第二位"b"与S串中第二位已经判断相等，意味着T中首字符"a"与第二位"b"不需要判断也知道他们不相等，则"b"——"e"的判断都可忽略
*所以步骤2-5均可忽略，只保留步骤1、6就已经判断完成了。之所以保留T6是因为第1步中已经判断了T6 != S6，但是不知道T1是否=S6。
*对于子串中有与首字母相等的字符时，可以省略一些不必要的步骤，即主串的i值不用回溯。
*对于j值，如果ST有相等字符，则j一定变动，即与主串无关，取决于T中结构的相似度。
    整个算法复杂度O(n+m) < O((n-m+1)*m) 
    KMP算法仅当模式与主串之间存在许多“部分匹配”的情况下才体现出它的优势，否则两者差异不明显。

# 树(Tree)
    树是n个节点的有限集，n = 0时为空树。在任意一颗非空树中：
        1.有且仅有一个特定的成为根(Root)的节点
        2.当n > 1时，其余节点可分为m个互不相交的有限集T1、T2……Tn，其中每一个集合本身又是一棵树，并且成为根的子树(SubTree)
    节点：
        1.包含一个数据元素及若干指向其子树的分支，节点拥有的子树数称为节点的度(Degree)
        2.度为0的节点成为叶节点(Leaf)或终端节点
        3.除根节点外，分支节点也称为内部节点
        4.树的度是树内各节点的度的最大值
        5.子节点(Child)，父节点(Parent)，兄弟节点(Sibling),祖先/子孙：从根到该节点所经分支上的所有节点
    节点的层次(Level)：
        1.从根开始定义，根为第一层，根的子节点为第二层，比如：某节点在第x层，根就在x+1层
        2.父节点在同一层的节点互为堂兄弟，树中节点的最大层次称为树的深度(Depth)或高度
    特性:
        1.非线性结构，一对多。
        2.根节点唯一，子树个数无限制但互不相交
        3.树中节点的子树是从左至右有顺序的，不能互换，则成为有序树，否则为无序树
        4.森林(Forest)是n棵互不相交的树的集合，对于树中的每个节点，其子树的集合即是森林
    与线性表比较：
        线性结构：第一个数据元素：无前驱
                 最后一个数据元素：无后继
                 中间元素：一个前驱一个后继
        树结构：根节点：无双亲，唯一
                叶节点：无子节点，可多个
                中间节点：一个父节点及多个子节点
## 树的存储结构
    需要同时运用顺序存储以及链式存储
    双亲表示法：
        1.树除了根节点外的所有节点一定有父节点，可以没有子节点。所以需要有数据域 data 和指针域 parent
        2.由于根节点无父节点，则根节点的位置域 = -1
        3.若从子节点找父节点，有指针，时间复杂度O(1)
        4.若从父节点找子节点，需要遍历。则需增加一个长子域，可以找到同一层的其他子节点。无其他子节点则长子域 = -1
        5.还需增加右兄弟域，来体现兄弟关系，若右兄弟不存在，则赋值-1
    孩子表示法：
        多重链表表示法：树中每个节点可能有多棵子树，即每个节点有多个指针域，其中每个该指针指向一棵子树的根节点。
            1.树的度数很少，指针域的个数就等于树的度。比如树的度为3，就创建3个指针域：data | child1 | child2 | child3
            2.这样如果度很多则很多指针域为空，浪费存储空间
        若充分利用空间：每个节点指针域的个数等于该节点的度，再专门取一个位置存储节点指针域的个数：data | degree | child1 | child2 | …… | childn
            这种方法不浪费空间，但是各节点都是不同结构的链表，还需维护节点的度的数值，浪费时间。
        孩子表示法：
            1.把每个节点的子节点排列起来，以单链表作存储结构，则n个节点有n个叶节点，则此单链表为空。然后n个头指针又组成一个线性表，采用顺序存储结构，存放进一个一维数组中。
            2.子链表的子节点： child | next，child数据域，存某个节点在表头数组中的下标，next指针域，存只想某节点的下一个子节点的指针
            3.表头数组的表头节点： data | firstchild，data数据域，存某节点的数据信息，firstchild头指针域，存某节点子链表的头指针
            4.要查找某个节点的子节点或者兄弟节点时，只需找这个节点的子单链表就可以
            5.需要遍历才直到父节点
    孩子兄弟表示法：
        任意树，节点的第一个孩子如果存在就是唯一的，右兄弟如果存在也是唯一的，因此设置两个指针，分别指向该节点的第一个子节点和其右兄弟
        data | firstchild | rightsib
        数据域    指针域      指针域     firstchild存第一个子节点的存储地址，rightsib存右兄弟节点的存储地址
        若想找父节点则可再加parent指针
        即把复杂的树变成二叉树

## 二叉树(Bianry Tree)
    二叉树是n(n>=0)个节点的有限集合，该集合或者为空集，或者有一个根节点和两颗互不相交的、分别称为根节点的左子树和右子树和二叉树组成。
    二叉树的特点：
        1.每个节点最多有两棵子树，所以二叉树中不存在度 > 2的节点。注意不是只有两棵子树，而是最多有。没有字数或者有一棵子树都可以。
        2.左子树和右子树是有顺序的，次序不能任意颠倒。
        3.即使树中某节点只有一棵子树，也要区分它是左子树还是右子树。
    二叉树具有5种基本形态：
        1.空二叉树
        2.只有一个根节点
        3.根节点只有左子树
        4.根节点只有右子树
        5.根节点既有左子树又有右子树
    特殊二叉树：
        1.斜树：
            所有的节点都只有左子树的二叉树叫左斜树，右斜树同理，它们统称为斜树。
            每一层都只有一个节点，节点的个数与二叉树的深度相同。（线性表结构——是树的特殊表现形式）
        2.满二叉树：
            同一颗二叉树中，如果所有分支节点都存在左子树和右子树，并且所有叶子都在同一层上，成为满二叉树。
            判定标准：
                1.叶子只能出现在最下一层
                2.非叶子节点的度一定是2
                3.在同样深度的二叉树中，满二叉树的节点个数最多，叶子最多
        3.完全二叉树：
            对一棵具有n个节点的二叉树按层序编号，如果编号为i(1 <= i <= n)的节点与同样深度的满二叉树中编号为i的节点在二叉树中位置完全相同，则成为完全二叉树。
            满二叉树一定是完全二叉树，完全二叉树不一定是满的。
            特点：
                1.叶子节点只能出现在最下两层
                2.最下层的叶子一定计中在左部连续位置
                3.倒数二层，若有叶子节点，一定都在有部连续位置
                4.如果节点度为1，则该减点只有左孩子，即不存在只有右子树的情况
                5.同样节点数的二叉树，完全二叉树深度最小
                6.编号没有空挡
## 二叉树的性质
    1.在二叉树的第i层上至多有2 ^ i-1个节点(i >= 1)
    2.深度为k的二叉树至多有2^k - 1个节点(k >= 1)
    3.对任何一颗二叉树T，如果其终端节点数为n0，度为2的节点数为n2，则n0 = n2 + 1
    4.具有n个节点的完全二叉树的深度为[log2n] + 1 ([x]表示不大于x的最大整数)
        因为n = 2^k - 1，所以k = log2(n+1)
    5.如果对一棵有n个节点的完全二叉树（其深度为[log2n] + 1）的节点按层序编号，对任一节点i有：
        1.如果i = 1，则节点i是二叉树的根，无双亲；如果i > 1，择其双亲是节点[i/2]
        2.如果2i > n，则节点i无左孩子（i是叶子节点）；否则其左孩子是节点2i
        3.如果2i + 1 > n，则节点i无右孩子；否则有孩子是节点2i + 1
## 二叉树的存储结构
    由于定义严格，用顺序结构也可以体现出来二叉树结构
        对于一般二叉树，尽管层序编号不能反映逻辑关系，但可按其完全二叉树编号，把不存在的节点设置为“ ^ ”
        如果极端情况：深度为k的右斜树，只有k个节点，但要分配2^k - 1个存储单元空间，所以顺序存储结构一般只用于完全二叉树。
    二叉链表：
        二叉树每个节点最多有两个孩子，所以为它设计一个数据域与两个指针域
        lchild  |  data  |  rchild  data是数据域，lrchild是指针域
        如果有需要还可以增加一个指向其双亲的指针域，这样称之为三叉链表
## 遍历二叉树(traversing binary tree)
    指从根节点出发，按照某种次序依次访问二叉树中的所有节点，使得每个节点被访问一次且仅被访问一次
    1.前序遍历
        规则：若二叉树为空，则空操作返回，否则先访问根节点，然后前序遍历左子树，再前序遍历右子树
            ABDGHCEIF
    2.中序遍历
        规则：若树为空，则空操作返回，否则从根节点开始（注意不是先访问根节点），中序遍历根节点的左子树，然后访问根节点，最后中序遍历右子树
            GDHBAEICF
    3.后序遍历
        规则：若树为空，则空操作返回，否则从左到右先叶子后节点的方式遍历访问左右子树，最后访问根节点
            GHDBIEFCA
    4.层序遍历
        规则：若树为空，则空操作返回，否则从树的第一层也就是根节点开始访问，从上而下逐层遍历，在同一层按从左到右的顺序逐个访问
            ABCDEFGHI
    注意：一直前序和后序遍历是不能确定一棵二叉树的——无法确定节点为左子树还是右子树
## 建立二叉树
    先把普通二叉树用'#'不全叶子节点的子节点和缺少兄弟节点的节点，使每个节点都有两个子节点，称之为拓展二叉树
        AB#D##C##
## 线索二叉树
    除了满二叉树，其他所有二叉树的lrchild两个指针存在大量浪费，利用这些空地址存放指向节点再某种遍历次序下的前驱和后继
        这种只想前驱和后继的指针叫做线索，加上先做的二叉链表成为线索链表，相应的二叉树叫线索二叉树
        即若指针为NULL，则指向父节点data——转变成了双向链表
    对二叉树以某种次序便利使其变为线索二叉树的过程称作是线索化
        lrchild指向子节点还是后继需要一个区分标志，每个节点再增设两个标志域 ltag 和 rtag，只存放0或1的布尔型变量，占用内存小于lrchild指针变量
            lchild  |  ltag  |  data  |  rtag  |  rchild
        ltag = 0时指向左孩子，为1时指向该节点前驱
        rtag = 0时指向右孩子，为1时指向该节点后继
    线索化的过程就是在遍历过程中修改空指针的过程 —— 即操作双向链表
    由于充分利用了空指针域的空间，如果需要经常遍历或者查找结点需要某种遍历序列的前驱和后继，那么可用线索二叉树存储结构
## 树、二叉树、森林的转换
    树 —— 二叉树
        1.加线。在所有兄弟节点之间加一条线
        2.去线。对书中每个节点只保留与第一个子节点的连线，删除与其他子节点的连线
        3.层次调整。以树的根节点为轴心，将树顺时针旋转一定角度，第一个子节点是其左子节点，兄弟节点的子节点是右节点
    森林 —— 二叉树
        1.每个数转换为二叉树
        2.第一棵二叉树不懂，从第二棵开始依次把后一棵二叉树的根节点作为前一棵二叉树的右子节点，用线连起来
    二叉树 —— 树
        1.加线。将左子节点的n个右子节点都作为此节点的子节点，将该节点与这些右子节点连线
        2.去线。删除原二叉树中所有节点与右子节点的连线
        3.层次调整
    二叉树 —— 森林
        判断二叉树能否转换成树or森林：看根节点有没有右子节点，有就是森林，没有就是树
        1.从根节点开始，若右子节点存在，则删除右子节点的连线，再看分离后的二叉树右子节点是否存在……直到所有右子节点都删除为止得到分离的二叉树
        2.将每个分离后的二叉树转换为树
## 赫夫曼树（压缩编码方法）
    二叉树中叶子节点带权
    从树中一个节点到两一个节点之间的分支构成两个节点之间的路径，路径上的分支数目称作路径长度
    树的路径长度就是从树根到每一节点的路径长度之和。其中带权路径长度WPL最小的二叉树称作赫夫曼树——最优二叉树

# 图
## 图的各种定义
    图(Graph)：是由顶点的有穷非空集合和顶点之间边的集合组成，通常表示为：G(V,E)，其中G表示图，V是图G中顶点的集合，E是图G中边的集合
        1.线性表中把数据元素叫元素，树中数据元素叫节点，图中数据元素叫顶点(Vertex)
        2.空表空树，图中不允许为空图，必须有顶点，顶点集合V 有穷非空
        3.线性表中数据元素有线性关系，树中数据元素有层次关系，图中任意两个顶点之间都有可能有关系 ，顶点之间逻辑关系用边来表示，边集可以为空。
    无向边：若顶点v1到vj之间的边没有方向，则这条边为无向边。表示为无需偶对(v1,vj)或(vj,v1)。若任意两顶点间的边都是无向边，则该图为无向图。
    有向边：若顶点v1到vj之间的边有方向，则这条边为有向边。也成为弧(Arc)，表示为<v1,vj>，v1为弧头，vj为弧尾。
    简单图：图中若不存在顶点到其自身的边，且同一条边不重复出现，则成为简单图。
    无向完全图：在无向图中，如果任意两个顶点之间都存在边，则称该图为无向完全图。所以m个顶点的无向完全图有n*(n-1)/2条边。
    有向完全图：在有向图中，如果任意两个顶点之间都存在方向互为相反的两条弧，则称该图为有向完全图。n个顶点有n*(n-1)条边。
    有很少条边或弧的图叫稀疏图，反之叫稠密图。
    与图的边或弧相关的数叫权(Weight)，带权的图通常成为网(Network)
    若两个图G = (V, {E}), G' = (V', [E']), V'属于V，E'属于E，则G'为G的子图。
## 顶点和边的关系
    对于无向图G = (V, {E})，如果(V,V')属于E，则V和V'相邻接。边(V,V')依附于顶点V,V'。顶点V的度(Degree)是个V相关联的边的数量。记为TD(V)
    对于有向图G = (V, {E})，如果<V,V'>属于E，则V邻接到V'，V'临界自V。以顶点V为头的弧的数量成为V的入度(InDegree)，记为ID(v)。以V为尾的弧的数量叫V的出度(OutDegree),记为OD(V)。顶点V的度为TD(V) = ID(V) + OD(V)
    无向图G = (V, {E})中从顶点V到顶点V'的路径(Path)是一个顶点序列。
    路径的长度是路径上边或弧的数目。
    第一个顶点到最后一个顶点相同的路径成为回路或环(Cycle)。序列中顶点不重复出现的路径称为简单路径。除了第一个顶点和最后一个顶点之外，其余顶点不重复出现的回路，称为简单回路或简单环。 
## 连通图相关术语
    在无向图G中，如果每一对Vi,Vj属于V，从Vi到Vj都存在路径，则称G是强连通图。有向图中的极大强连通子图称作有向图的强连通分量。
    连通图的生成树：一个连通图的生成树是一个绩效的连通子图，含有图中全部的n个顶点，但只有足以构成一棵树的n-1条边。
    如果一个有向图恰有一个顶点的入度为0，其余顶点的入度均为1，则是一颗有向树。
    一个有向图的生成森林由若干棵有向树组成，含有途中全部顶点，但只有足以构成若干棵不相交的有向树的弧。
## 图的存储结构
    图不能用简单的顺序存储结构表示
    邻接矩阵：图是由顶点和边/弧组成，分两个结构存储，定点不分大小、主次，所以用一维数组表示，边/弧时顶点间的关系，用二维数组表示。
        图的邻接矩阵(Adjencency Matrix)存储方式是用两个数组表示图，一个一维数组存储图中顶点信息，一个二维数组(称作邻接矩阵)存储图中边/弧的信息。