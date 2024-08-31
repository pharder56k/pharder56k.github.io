---
title: "Blowfish主题常用简码的使用说明"
date: 2024-08-31T10:11:39+08:00
draft: false
tags: ["hugo", "blowfish"]
categories: ["使用技巧"]
featureimage:
---

[Blowfish简码](https://blowfish.page/zh-cn/docs/shortcodes)


# 简码的使用
## Alert

`alert` 可以将其中内容输出为文章中的风格化消息框。它对于吸引读者注意您不想让读者错过的重要信息很有用。

<!-- prettier-ignore-start -->
| 参数        | 功能                                                                                                                             |
| ----------- | -------------------------------------------------------------------------------------------------------------------------------- |
| `icon`      | **可选** 显示在左侧的图标。<br>**默认：** `exclaimation triangle icon` (查看[图标简码](#icon)，了解有关使用图标的更多详细信息。) |
| `iconColor` | **可选** 基本 CSS 样式中图标的颜色。<br>可以是十六进制值 (`#FFFFFF`) 或颜色名称 (`white`)<br>默认情况下由当前配色方案决定。      |
| `cardColor` | **可选** 基本 CSS 样式中卡片背景的颜色。<br>可以是十六进制值 (`#FFFFFF`) 或颜色名称 (`white`)<br>默认情况下由当前配色方案决定。  |
| `textColor` | **可选** 基本 CSS 样式中文本的颜色。<br>可以是十六进制值 (`#FFFFFF`) 或颜色名称 (`white`)<br>默认情况下由当前配色方案决定。      |
<!-- prettier-ignore-end -->

输入内容是用 Markdown 语言编写的，因此您可以根据需要设置其格式。

**例1:** 无参数

```md
{{</* alert */>}}
**警告！**此操作具有破坏性！
{{</* /alert */>}}
```

{{< alert >}}
**警告！**此操作具有破坏性！
{{< /alert >}}

**例2:** 未命名参数

```md
{{</* alert "twitter" */>}}
Don't forget to [follow me](https://twitter.com/nunocoracao) on Twitter.
{{</* /alert */>}}
```

{{< alert "twitter" >}}
Don't forget to [follow me](https://twitter.com/nunocoracao) on Twitter.
{{< /alert >}}

**例3:** 命名参数

```md
{{</* alert icon="fire" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" */>}}
This is an error!
{{</* /alert */>}}
```

{{< alert icon="fire" cardColor="#e63946" iconColor="#1d3557" textColor="#f1faee" >}}
This is an error!
{{< /alert >}}

<br/><br/><br/>

## Badge

`badge` 输出一个美观的徽章组件，该组件对于显示元数据很有用。

**例如：**

```md
{{</* badge */>}}
New article!
{{</* /badge */>}}
```

{{< badge >}}
New article!
{{< /badge >}}

<br/><br/><br/>

## Button

`button` 输出一个样式化的按钮组件，可用于突出显示主要操作。它有三个可选变量 `href`、`target` 和 `rel`，可用于指定链接的 URL、目标和关系。

**例如：**

```md
{{</* button href="#button" target="_self" */>}}
Call to action
{{</* /button */>}}
```

{{< button href="#button" target="_self" >}}
Call to action
{{< /button >}}

<br/><br/><br/>

## GitHub 卡片

`github` 允许您快速链接到 github Repo，同时显示和更新有关它的实时统计信息，例如它的 star 和 fork 数。

<!-- prettier-ignore-start -->
| 参数   | 功能                                           |
| ------ | ---------------------------------------------- |
| `repo` | [String] 格式为 `username/repo` 的 github repo |
<!-- prettier-ignore-end -->

**例1:**

```md
{{</* github repo="nunocoracao/blowfish" */>}}
```

{{< github repo="nunocoracao/blowfish" >}}

<br/><br/><br/>


## 重点突出


`keyword` 组件可用于在视觉上突出显示某些重要的单词或短语，例如专业技能等。 `keywordList` 简码可用于将多个 `keyword` 组合在一起。每个组件可以具有以下参数。


<!-- prettier-ignore-start -->
| 参数   | 功能                        |
| ------ | --------------------------- |
| `icon` | **可选** 关键字中使用的图标 |
<!-- prettier-ignore-end -->

输入内容是用 Markdown 编写的，因此您可以根据需要设置其格式。

**例1 :**

```md
{{</* keyword */>}} Super skill {{</* /keyword */>}}
```

{{< keyword >}} *Standalone* skill {{< /keyword >}}

**例2 :**

```md
{{</* keywordList */>}}
{{</* keyword icon="github" */>}} Lorem ipsum dolor. {{</* /keyword */>}}
{{</* keyword icon="code" */>}} **Important** skill {{</* /keyword */>}}
{{</* /keywordList */>}}

{{</* keyword */>}} *Standalone* skill {{</* /keyword */>}}
```

{{< keywordList >}}
{{< keyword icon="github" >}} Lorem ipsum dolor {{< /keyword >}}
{{< keyword icon="code" >}} **Important** skill {{< /keyword >}}
{{< /keywordList >}}
{{< keyword >}} *Standalone* skill {{< /keyword >}}

<br/><br/><br/>

## 时间线

`timeline` 创建了一个可视化时间线，用于展示专业经验、项目成就等。 `timeline` 简码依赖于 `timelineItem` 子简码来定义主时间线中的每个项目。每个项目可以具有以下属性。

<!-- prettier-ignore-start -->
| 参数        | 功能                     |
| ----------- | ------------------------ |
| `icon`      | 要在时间线中使用的图标。 |
| `header`    | 每个条目的标题           |
| `badge`     | 放置在右上角徽章内的文本 |
| `subheader` | 每个条目的副标题         |

<!-- prettier-ignore-end -->

**例如：**

```md
{{</* timeline */>}}

{{</* timelineItem icon="github" header="header" badge="badge test" subheader="subheader" */>}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus non magna ex. Donec sollicitudin ut lorem quis lobortis. Nam ac ipsum libero. Sed a ex eget ipsum tincidunt venenatis quis sed nisl. Pellentesque sed urna vel odio consequat tincidunt id ut purus. Nam sollicitudin est sed dui interdum rhoncus.
{{</* /timelineItem */>}}


{{</* timelineItem icon="code" header="Another Awesome Header" badge="date - present" subheader="Awesome Subheader" */>}}
With html code
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
{{</* /timelineItem */>}}

{{</* timelineItem icon="star" header="Shortcodes" badge="AWESOME" */>}}
With other shortcodes
{{</* gallery */>}}
  <img src="gallery/01.jpg" class="grid-w33" />
  <img src="gallery/02.jpg" class="grid-w33" />
  <img src="gallery/03.jpg" class="grid-w33" />
  <img src="gallery/04.jpg" class="grid-w33" />
  <img src="gallery/05.jpg" class="grid-w33" />
  <img src="gallery/06.jpg" class="grid-w33" />
  <img src="gallery/07.jpg" class="grid-w33" />
{{</* /gallery */>}}
{{</* /timelineItem */>}}

{{</* timelineItem icon="code" header="Another Awesome Header"*/>}}
{{</* github repo="nunocoracao/blowfish" */>}}
{{</* /timelineItem */>}}

{{</* /timeline */>}}
```


{{< timeline >}}

{{< timelineItem icon="github" header="header" badge="badge test" subheader="subheader" >}}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vivamus non magna ex. Donec sollicitudin ut lorem quis lobortis. Nam ac ipsum libero. Sed a ex eget ipsum tincidunt venenatis quis sed nisl. Pellentesque sed urna vel odio consequat tincidunt id ut purus. Nam sollicitudin est sed dui interdum rhoncus.
{{</ timelineItem >}}


{{< timelineItem icon="code" header="Another Awesome Header" badge="date - present" subheader="Awesome Subheader">}}
With html code
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>
{{</ timelineItem >}}

{{< timelineItem icon="star" header="Shortcodes" badge="AWESOME" >}}
With other shortcodes
{{< gallery >}}
  <img src="gallery/01.jpg" class="grid-w33" />
  <img src="gallery/02.jpg" class="grid-w33" />
  <img src="gallery/03.jpg" class="grid-w33" />
  <img src="gallery/04.jpg" class="grid-w33" />
  <img src="gallery/05.jpg" class="grid-w33" />
  <img src="gallery/06.jpg" class="grid-w33" />
  <img src="gallery/07.jpg" class="grid-w33" />
{{< /gallery >}}
{{< timelineItem icon="code" header="Another Awesome Header">}}
{{< github repo="nunocoracao/blowfish" >}}

{{</ timelineItem >}}
{{</ timelineItem >}}

{{</ timeline >}}


<br/><br/><br/>

## Youtube 嵌入播放器

使用 [lite-youtube-embed](https://github.com/paulirish/lite-youtube-embed) 库嵌入 YouTube 视频的简码。该库是 YouTube 嵌入播放器的轻量级替代品，其设计速度更快、更高效。

<!-- prettier-ignore-start -->
| 参数    | 功能                                |
| ------- | ----------------------------------- |
| `id`    | [String] 要嵌入的 YouTube 视频 ID。 |
| `label` | [String] 视频的标签                 |
<!-- prettier-ignore-end -->

**例1:**

```md
{{</* youtubeLite id="SgXhGb-7QbU" label="Blowfish-tools demo" */>}}

```

{{< youtubeLite id="SgXhGb-7QbU" label="Blowfish-tools demo" >}}