---
layout: article
title:  "Unity脚本生命周期"
categories: unity
image:
    teaser: /unity/unity.jpg
---
> 简洁： 在unity脚本生命周期中的各个函数使用时总结的心得

## Unity Script ExecutionOrder
 
- 官方API手册地址： [https://docs.unity3d.com/Manual/ExecutionOrder.html](https://docs.unity3d.com/Manual/ExecutionOrder.html)
- 本地API手册：<br>
	如果安装Unity 时下载有离线文档，Unity文档在以下路径：
	![unityAPI_local](/images/unity/utniy_01/UnityAPI_Local.jpg)
<br>
Unity Lifecycle Flowchart :
![lifecycle_01](/images/unity/unity_01/ScriptLifecycle_01.jpg)
![lifecycle_02](/images/unity/unity_01/SceiptLifecycle_02.jpg)

### Reset
---
只在编辑模式下被调用， 在检查面板的Reset按钮或者首次添加该组件时被调用<br>
在Unity2018 API中Reset被放到 Initialization之后 ，由于只在编辑模式调用，因此不会影响运行模式下的脚本方法顺序
### Initialization
---
1. Awake（）<br>
Unity最先执行的方法，在开始执行后，所有启用的物体上的脚本均会被执行，但仅执行一次<br>
是启用的物体 ！！<br>
如果在运行时进入场景 ，gameobject A处于未启用状态，此物体上脚本的Awake方法不会执行，但当此物体在运行时被激活后，Awake方法会被执行<br>
另外新创建的物体也会先执行 Awake方法
2. OnEnable（）<br>
当执行完Awake（）后 或者 禁用的物体被启用后 此方法会被调用<br>
此方法可以被执行多次
3. Start（）<br>
同 Awake方法，与之不同的是 执行顺序在Awake与OnEnable之后


