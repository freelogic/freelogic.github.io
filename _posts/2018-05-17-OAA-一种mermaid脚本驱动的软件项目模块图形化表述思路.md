---
layout: post
title: 2018-05-17-OAA-一种mermaid脚本驱动的软件项目模块图形化表述思路
key: 20180517
tags: OAA flow chart sequence diagram 泳道图 时序图 图表 OAA PM Master
modify_date: 05-17
---



# OAA-一种mermaid脚本驱动的软件项目模块图形化表述思路

说明：
* 本文发布于: [gitee](http://freelogic.gitee.io/webpost/),[github](https://freelogic.github.io/),[博客园](http://www.cnblogs.com/taichu/)
* 转载和引用请指明原作者和连接及出处.

正文：

* 说明：这里记录了如何使用mermaid脚本语言来作图，从而更清晰明了的表述软件项目的模块关系及信令数据交互流程，作为软件工程和管理的一种必备手段和方法论建议。


# OAA

## 目的
* “OAA”即“One Picture Above All”，含义是“一张图，胜千言”。
* 我们期望用脚本语言来画图，并方便观看，而图是描述信令流和数据流的好方法。
  * 我们只考虑两种图：“flow chart”流程图和“sequence diagram”时序图（也叫“泳道图）。
      * “flow chart”：描述组网拓扑结构和模块实体间的关系；
      * “sequence diagram”：描述多个网元之间回合制的信令和数据交互的时序信息；
  * 结合使用这两张图，一般就能描述绝大多数的工程和项目场景。
* 用mermaid脚本语言还有格外的好处如下：
  * 脚本语言，容易编辑和维护，比二进制的诸如word/powerpoint，及图形JPG要方便；
  * 基于字符串，方便合并，观察，版本维护，放入GIT/SVN非常的小；
  * 文件小，方便随意的黏贴，拷贝，交互，传输，讨论和修改；
* 总之，OAA是一种态度和方法论，用不用随你项目和人力而定，建议使用；      


## 说明
* 本项目是作为脚本作图语言mermaid的一个使用的例子，方便使用者继续创作脚本图；
* 信息：
  * [mermaid官网](https://mermaidjs.github.io/flowchart.html)；
  * [mermaid在线测试](https://mermaidjs.github.io/mermaid-live-editor/)
  * [mermaid源码@github](https://github.com/knsv/mermaid)（可惜的是release发布到7.0.0只有就没了，作者似乎不在github维护了！）
  * [mermaid源码@https://unpkg.com/mermaid@xxx/dist/](https://unpkg.com/mermaid@8.0.0-rc.8/)，请自行选择版本；
      * 其中“dist”目录用于JS当中的CDN方式引用“mermaid.min.js”等；
      * 其中“src”目录用于查看源码（比如github上不维护的版本新！已经到了8.X版本了！）
      * 另外，源码中作者用scss的格式存放可编译的css的源码，scss文件可以通过指定的编译器生成为目标css。
  * CDN调用方式如下：

```
<script src="https://unpkg.com/mermaid@8.0.0-rc.8/dist/mermaid.min.js"></script>
```

## 使用
* 请从[OAA@Gitee](https://gitee.com/freelogic/OAA)项目查看具体情况，建议项目经理PM或敏捷开发Master可以了解下。

## Example

* ![图例(label)]({{ "/assets/images4post/label.jpg" | absolute_url }})

* ![流程图(flowchart)]({{ "/assets/images4post/flowchart.jpg" | absolute_url }})

* ![时序图(泳道图/sequence diagram)]({{ "/assets/images4post/sequencediagram.jpg" | absolute_url }})



## END
