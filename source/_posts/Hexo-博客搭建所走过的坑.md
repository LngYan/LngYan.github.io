---
title: Hexo-博客搭建
categories:
  - Hexo
  - blog
tags:
  - 博客
  - 个人网站
---
## 前沿
### 为何搭建博客
建立博客的想法是在学习中以为老师推荐的，后来，随着个人知识面的拓展和深入，发现有太多的知识和经验值得沉淀和交流，在某年没有回家过春节的时候沉下心来搭建了一个博客，算是自己有一个回顾复盘的地方了吧。

另外，根据“学习金字塔”理论（Edgar Dale，1946），**对知识进行演示、实践和传授能够显著提升学习保持率**，而沉淀为博客或视频正是这样一种形式，我认为一方面可以让无形的知识转为有形的博客，便于之后复习和追溯，另一方面通过沉淀转化可以提高我对知识的记忆和掌握水平。

### 建设原理

博客自然是重内容，轻形式，主要重心点放在内容上，仅保留少量的交流功能即可。

这里我使用 [Hexo](https://hexo.io/) 框架搭建博客，该框架基于 [Node.js](https://nodejs.org/zh-cn/) ，使用者不需要掌握 node 原理，[Hexo](https://hexo.io/) 会根据配置项中预设好的模板自动将内容转换为静态页面。

Hexo 提供了多种形式的主题：这里我选用的是 [Diaspora](https://github.com/Fechin/hexo-theme-diaspora)。该主题较为贴近我对博客美观性的要求，且原生支持一系列配置项和插件，能满足我的需要。

虽然我有自己的NAS，但是为了提高其可用性，我还是白嫖了 GitHub Pages 服务，将 Hexo 生成的静态页面部署上去，从而可以让大家访问。
## 基础环境安装

### 安装 Node.js

直接到官网上下载安装即可https://nodejs.org/en/download/

- Node.js (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
- Node自带npm

安装完成后在终端运行如下命令：

```
$ node -v
$ npm  -v
```

如果正常响应对应版本号，则说明安装及环境变量配置成功。

### 安装Git

安装Git需要用到安装器，我电脑上已安装HomeBrew所以可以直接安装
```
 brew install git   // 安装Git
```
也可以下载[安装程序](https://sourceforge.net/projects/git-osx-installer/)来安装

### 安装 Hexo

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
成功运行后，即可使用 hexo 的命令对该目录进行操作了
HEXO-博客搭建P1.png
![upload successful](/images/pasted-1.png)
运行：
```
$ hexo server
```
即可从本地运行博客服务器。浏览器打开终端提示的页面(默认为 https://localhost:4000)，即可查看。

默认页面为内置的 hello-world.md 文档。至此我们已经完成了 [Hexo](https://hexo.io/zh-cn/)的安装，如要了解更多配置项可参考[Configuration | Hexo](https://hexo.io/zh-cn/api/)，要了解更多 Hexo 命令可参考 [Commands | Hexo](https://hexo.io/zh-cn/api/)。

### 主题安装

为了使博客不太难看，我们需要安装一个主题就拿我目前用的[Diaspora](https://github.com/Fechin/hexo-theme-diaspora)主题来举例，进入安装Hexo目录，安装主题：

```
$ cd <folder>
$ git clone https://github.com/Fechin/hexo-theme-diaspora.git themes/diaspora
```

安装完成后在theme文件夹内会多出一个名为Diaspora(刚刚安装的主题）文件夹就说明安装成功了
接下来启动和设置主题，修改Hexo配置文件 `_config.yml` 主题项设置为diaspora

```
theme: diaspora
```

如何设置主题可以在[Diaspora](https://github.com/Fechin/hexo-theme-diaspora)里查询

注意：请在更时主题时备份 `_config.yml`配置文件

配置好主题后重新启动hexo你的博客就更新为你设置的主题啦

```
$ hexo s
```
当然Hexo还有非常多的主题供你选择。

### 写文章
所有基础框架都已经创建完成，接下来可以开始写你的第一篇博客了
在`/source/_posts`下创建你的第一个博客吧，例如，创建一个名为`FirstNight.md`的文件，用Markdown大肆发挥吧，注意保存。
```
 ---
 title: First Night
 ---
 > 我有一头**小毛驴**，可是我从来都不骑。
```


### 发布
测试没问题后，我们就生成静态网页文件发布至我们的Github pages 中或者自己的服务器上，国内的话可以发布到[gitee](https://gitee.com/)上访问会快一些，毕竟git是国外网站，懂得都懂。
**在线发布**
首先自己先注册个账号，注册过程可能需要验证你的邮箱，其他就不在赘述。

配置 Github 仓库：

需要创建一个仓库(repository) 来存储我们的网站，点击首页任意位置出现的 New repository按钮创建仓库, Respository name 中的`username.github.io `的username 一定与前面的Owner 一致，记住你的`username`下面会用到。
HEXO-博客搭建P2.png
![upload successful](/images/pasted-2.png)

将 Hexo 文件夹中的文件 push 到储存库的默认分支，默认分支通常名为 main，旧一点的储存库可能名为 master。
- 将 **main** 分支 push 到 GitHub：
```
$ git push -u origin main
```
- 默认情况下 public/ 不会被上传(也不该被上传)，确保 .gitignore 文件中包含一行 public/。整体文件夹结构应该与 范例储存库 大致相似。

使用 node --version 指令检查你电脑上的 Node.js 版本，并记下该版本 (例如：`v16.y.z`)
在储存库中建立 `.github/workflows/pages.yml`（特别注意路径我就踩过坑把文件存在了根目录下），并填入以下内容 (将 16 替换为上个步骤中记下的版本)：

```
.github/workflows/pages.yml

name: Pages
on:
  push:
    branches:
      - main # default branch
jobs:
  pages:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Use Node.js 16.x
        uses: actions/setup-node@v2
        with:
          node-version: "16"
      - name: Cache NPM dependencies
        uses: actions/cache@v2
        with:
          path: node_modules
          key: ${{ runner.OS }}-npm-cache
          restore-keys: |
            ${{ runner.OS }}-npm-cache
      - name: Install Dependencies
        run: npm install
      - name: Build
        run: npm run build
      - name: Deploy
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./public
```     

当部署作业完成后，产生的页面会放在储存库中的 gh-pages 分支。
    在储存库中前往 Settings > Pages > Source，并将 branch 改为 gh-pages。
    
HEXO-博客搭建P3.png
![upload successful](/images/pasted-3.png)

过几分钟后，访问上方的网站，就可以看见你博客就搭建成功啦！

### 更多

[更多主题](https://hexo.io/themes/)
[更多插件](https://hexo.io/plugins/)