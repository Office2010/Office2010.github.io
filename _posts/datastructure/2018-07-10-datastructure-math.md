---
layout: article
title:  "链表"
categories: datastructure
image:
    teaser: /teaser/default.jpg
---
> 简介：本文用的是C#内置的双向链表

```

  // 1. 链表的声明以及节点的定义
        LinkedList<string> link = new LinkedList<string>();
        LinkedListNode<string> node_01 = new LinkedListNode<string>("first node");
        LinkedListNode<string> node_02 = new LinkedListNode<string>("seconde node");
        LinkedListNode<string> node_03 = new LinkedListNode<string>("third node");
        LinkedListNode<string> node_04 = new LinkedListNode<string>("forth node");

        // 2. 节点的加入
        link.AddFirst(node_01);
        link.AddAfter(node_01, node_02);
        link.AddAfter(node_02, node_04);
        link.AddBefore(node_04, node_03);

        // 3. 计算包含的数量
        Debug.Log(link.Count);

        // 4. 遍历
        LinkedListNode<string> current = link.First;
        while (current != null)
        {
            Debug.Log(current.Value);
            current = current.Next;
        }

```

# 简单语法使用
---
教程： [markdown教程](https://www.zybuluo.com/mdeditor?url=https%3A%2F%2Fwww.zybuluo.com%2Fstatic%2Feditor%2Fmd-help.markdown)

1. 标题 <br>
![markdown_01](/images/others/markdown/markdown_01.jpg)

2. 链接、图片<br>
连接的格式为：`[百度连接](www.baidu.com)`
<br>图片的格式为：`![图片](/images/image_01.jpg)`
<br>注意区别,图标比连接格式多了一个 ！ 字符。

3. 有序、无序列表<br>
![markdown_02](/images/others/markdown/markdown_02.jpg)

4. 粗体和斜体<br>
使用 * 和 ** 表示斜体 和 粗体。
示例 ： 这是 *斜体*，这是**粗体**。

5. 行内代码块<br>
使用 `` <br>
示例： 这是个`行内代码块`。
6. 代码块<br>
使用两个\`\`\` <br>
示例：

```
void function_1(){
 Debug.Log("hello world");
}
```
<br> &nbsp;&nbsp;
7. 公式类<br>
示例：`n<sup>2</sup>=n<sub>x</sub>+1`：n<sup>2</sup>=n<sub>x</sub>+1
<br>[参考连接](https://www.jianshu.com/p/80ac23666a98)