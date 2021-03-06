---
layout: post
title: 数据结构整理之树
tags: 数据结构

---

二叉树的性质、树和森林、赫夫曼树、树的计数

1. 二叉树的性质

   1. 对任何一颗二叉树T，其终端结点数为n0，度为2的结点数为n2，则n0=n2+1。证明方法：设其总结点数为n，度为1的 结点数为n1，n=n0+n1+n2，设分支数为B 则n=B+1，又由于这些分支为度为1或2的结点射出的，所以有B=n1+2n2 联立可得。**思想：由分支数和结点数的关系得出**
   2. **对一颗完全二叉树**:如果i>1,则其双亲为不大于i/2的整数，**推论**：结点i的左孩子为2i（2i<=n），结点i的右孩子为2i+1.

2. 二叉树的存储结构

   链式存储结构：二叉链表，三叉链表（多了一个指针域指向父亲结点）

3. 遍历二叉树（**递归思想**）

   时间复杂度：O（n），空间复杂度：O（n）

4. 线索二叉树

   叶子结点：lchild和rchild存放线索（方便找到前驱和后继）

   中序遍历找前驱和后继：后继：先找到其右子数，然后顺着其左指针往下直到左标志位1的结点。

   前驱：找到他的左子树，顺着其右指针往下直到右标志位1的结点。

#### 2.树和森林

1. 表示法

   1. 双亲表示法（原理：每一个结点有唯一指定的双亲结点）

      结点存放的是双亲结点

   2. 孩子表示法

      把每个节点的孩子节点排列起来，看成是一个线性表，以单链表作为存储结构，则n个节点有n个孩子链表。（书P137）

   3. 孩子兄弟表示法

      又称做二叉链表表示法。链表中的结点的两个链域分别指向该节点的第一个孩子节点和下一个兄弟节点。优点：易于实现找结点孩子的操作。如：要访问节点x的第i个孩子，只需要找到第一个孩子节点，然后沿兄弟节点走i-1步

2. 森林与二叉树的转换（基于孩子兄弟表示法）
   二叉树和树都可以用二叉链表表示，基于此可以把任意颗树与二叉树进行互换。
   把森林中第二颗树的根节点看成是第一棵树的根节点的兄弟（在二叉树中就表现为根节点的右子	树（还是根据孩子兄弟表示法））
   当以二叉链表作为树的存储结构时，树的先根遍历和后根遍历可借用二叉树的先序遍历和中序遍历实现
#### 3.赫夫曼树   

1. 最优二叉树（赫夫曼树）
   1. 赫夫曼树的构造：在所给的权值中选取两棵根节点的权值最小的树作为左右子树构造一颗新的二叉树，且置新的二叉树的根节点的权值为其左、右子树上根节点的权值之和。
   2. 赫夫曼树不是唯一的，对于一颗已经构造好的赫夫曼树，赫夫曼编码是唯一的

#### 4.树的计数

1. **对含有n个结点的二叉树**：不相识的有1/(n+1)C2n,n颗
2. **对含有n个结点的树**：1/nC2n-1,n-1颗





