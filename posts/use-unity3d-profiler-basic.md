<!-- 
.. title: Use Unity3d Profiler Basic
.. slug: use-unity3d-profiler-basic
.. date: 2015-04-15 21:23:36 UTC+08:00
.. tags: u3d
.. category: 
.. link: 
.. description: 
.. type: text
-->

## 使用Unity3d Profiler进行性能优化---基础篇

初到项目组，还是应该做一些有特色的东西，于是想到除了在功能上多做支持外，必须在专项上给到一定的支持，
正好这个时候项目组还是很关注客户端性能的，自然的就接手这一块东西了。

以前对客户端性能的了解不算太多，而我们的游戏采用unity3d进行的开发，刚接手这块东西，自然就会想到是否引擎上有自带
的支持工具，简单一搜一大堆的Profiler介绍，于是便从Profiler着手开始学习和进行性能优化。

以下简单总结下这几日的使用心得和一些注意事项：

### 1.使客户端支持Profiler性能调优

要想使得客户端能够直接使用Profiler进行调优，那么在编译客户端的时候必须勾选`development`选项，如果是自行封装的命令行编译
也可在其中加上相应的选项以支持development。

### 2.通过development版本进行性能版本收集与分析

使用android真机连接profiler进行性能分析时，需要先执行`adb forward tcp:54999 localabstract:Unity-进程名`，执行成功后，
运行游戏，运行profiler，如果没问题就可以看到profiler收集到的性能数据了

### 3.关注的数据

在profiler中我们通常关注cpu，render，memory，观察游戏场景中的曲线走势图，选择游戏中的某点查看该点对应的函数执行，贴图信息。
但需要注意profiler不能往回查看以前的信息，不过我们可以在收集到疑似问题点后，点击`record`暂停纪录，然后分析疑似问题点。
当然比较方便的是直接开启两个profiler对比同一场景中的函数运算，场景贴图信息。
设置开启两个unity的方法：`Edit`->`preference`->`open project dialog always`。

