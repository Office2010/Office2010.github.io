---
layout: article
title:  "链表"
categories: datastructure
image:
    teaser: /datastructure/datastructure.jpg
---
> 简介：本文用的是C#内置的双向链表

## C#内置链表
内置链表为双向链<br>
```

  		 // 1. 链表的声明以及节点的定义
        LinkedList<string> link = new LinkedList<string>();
        LinkedListNode<string> node_01 = new LinkedListNode<string>("first node");
        LinkedListNode<string> node_02 = new LinkedListNode<string>("seconde node");
        LinkedListNode<string> node_03 = new LinkedListNode<string>("third node");
        LinkedListNode<string> node_04 = new LinkedListNode<string>("forth node");
        LinkedListNode<string> node_05 = new LinkedListNode<string>("five node");

        // 2. 节点的加入
        link.AddFirst(node_01);
        link.AddAfter(node_01, node_02);            //可做插入用
        link.AddAfter(node_02, node_04);            //可做插入用
        link.AddBefore(node_04, node_03);
        link.AddLast(node_05);

        // 3. 计算包含的数量
        Debug.Log(link.Count);

        // 4. 遍历
        LinkedListNode<string> current = link.First;
        while (current != null)
        {
            Debug.Log(current.Value);
            current = current.Next;
        }

        // 5. 查找节点
        var result = link.Find("forth node");
        if (result != null)
            Debug.Log("找到了此节点");

        // 6. 定位最后的节点
        var temp = link.Last;
        Debug.Log("最后一个节点为： " + temp.Value);

        // 7. 删除节点
        link.Remove("third node");
        link.Remove(node_04);
        link.Clear();                               // 删除全部节点

```

## 链表
---
链表是一种物理存储单元上非连续、非顺序的存储结构，数据元素是通过节点中的指针链接次序实现的。<br>

优点：<br>

+ 物理存储空间不一定是顺序存储，能灵活的内存动态管理<br>
+ 处理插入和删除操作方便，时间复杂度为O(1);
+ 链表长度不固定，可根据实际情况进行添加。


"双向链表的添加操作"
<br>
![link_01](/images/datastructure/link/link_01.jpg)<br>


双向链表的删除操作<br>
![link_02](/images/datastructure/link/link_02.jpg)