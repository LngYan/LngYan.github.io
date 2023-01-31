title: Hexo-博客搭建
categories:
  - 分类1
  - 分类2
tags:
  - 标签1
  - 标签2
author: 冷焱
date: 2023-01-31 10:13:34
mp3:
cover:
---
### 前沿
#### 为何搭建博客
建立博客的想法是在学习中以为老师推荐的，后来，随着个人知识面的拓展和深入，发现有太多的知识和经验值得沉淀和交流，在某年没有回家过春节的时候沉下心来搭建了一个博客，算是自己有一个回顾复盘的地方了吧。

另外，根据“学习金字塔”理论（Edgar Dale，1946），**对知识进行演示、实践和传授能够显著提升学习保持率**，而沉淀为博客或视频正是这样一种形式，我认为一方面可以让无形的知识转为有形的博客，便于之后复习和追溯，另一方面通过沉淀转化可以提高我对知识的记忆和掌握水平。

#### 建设原理

博客自然是重内容，轻形式，主要重心点放在内容上，仅保留少量的交流功能即可。

这里我使用 [Hexo](https://hexo.io/) 框架搭建博客，该框架基于 [Node.js](https://nodejs.org/zh-cn/) ，使用者不需要掌握 node 原理，[Hexo](https://hexo.io/) 会根据配置项中预设好的模板自动将内容转换为静态页面。

Hexo 提供了多种形式的主题：这里我选用的是 [Diaspora](https://github.com/Fechin/hexo-theme-diaspora)。该主题较为贴近我对博客美观性的要求，且原生支持一系列配置项和插件，能满足我的需要。

虽然我有自己的NAS，但是为了提高其可用性，我还是白嫖了 GitHub Pages 服务，将 Hexo 生成的静态页面部署上去，从而可以让大家访问。
#### 本地建设
##### 基础环境安装
###### 1.安装 Node.js

直接到官网上下载安装即可https://nodejs.org/en/download/

- Node.js (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
- Node自带npm

安装完成后在终端运行如下命令：

```
$ node -v
$ npm  -v
```

如果正常响应对应版本号，则说明安装及环境变量配置成功。

###### 2.安装Git

安装Git需要用到安装器，我电脑上已安装HomeBrew所以可以直接安装
```
 brew install git   // 安装Git
```
也可以下载[安装程序](https://sourceforge.net/projects/git-osx-installer/)来安装

###### 3.安装 Hexo

使用 npm（node 的包管理器，可以类比 python 的 pip）可以直接安装 Hexo。在终端输入如下命令开始安装

```
sudo npm install hexo-cli -g
```

检查是否安装正常。
```
hexo -v
```
安装后就可以开始配置了，选择一个本地文件夹作为博客的目录，终端切换到该目录下，初始化该目录并加载目录路径：
```
$ hexo init <folder>
$ cd <folder>
```
成功运行后，即可使用 hexo 的命令对该目录进行操作了，运行：
```
$ hexo server
```
即可从本地运行博客服务器。浏览器打开终端提示的页面（默认为 https://localhost:4000/），即可查看。

默认页面为内置的 hello-world.md 文档。至此我们已经完成了 Hexo 的安装，如要了解更多配置项可参考Configuration | Hexo，要了解更多 Hexo 命令可参考 Commands | Hexo。

###### 4.主题安装

为了使博客不太难看，我们需要安装一个主题，进入安装Hexo目录，安装主题

```
$ cd <folder>
```

拿我目前用的主题来举例，也是Hexo众多主题中最受欢迎的一个。上面出现的喵神的主题在这里。Hexo也有更多主题供你选择。
