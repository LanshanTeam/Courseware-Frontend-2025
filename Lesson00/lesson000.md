# 蓝山工作室前端组Lesson00（下）——了解Git

> 在学习本课程前，请确保你的电脑配置了Git环境，以及拥有了一个Github账号。如果没有，请翻阅上一篇课件。

# 1.前言

试想一下：

小王正在赶项目的关键功能，突然停电，电脑关机。因为没保存，他辛辛苦苦写的一下午，全没了！

小张和小秦一起参加寒假考核，本来合作做同一个项目。结果沟通不到位，两人同时在写同一个功能，用了两种完全不同的方法，最后在讨论该选用谁的代码成了一锅粥。

小牟拿到项目后没有思路，乱改了一通，把原本能跑的代码改得乱七八糟。结果发现跑不起来了，可是已经回不到之前正常运行的版本。

小沈作为项目组组长，项目上线后突然出现了 bug。他想找出是谁写的，却发现没人认账——小王说不是我，小张说我没动过，小秦说绝对没问题，小牟说我只是改了一点点……最后小沈什么也查不出来，被领导拉去“喝茶”了。

这一切，如果有了 **Git**，都会变得完全不同。

# 2.Git

在了解Git前，我们先要了解版本控制的概念。

## 2.1.版本控制

版本控制是指能够记录、管理文件或文件集合的内容及其随着时间推移发生的变化的系统。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=ZmM5YjAwN2ZlODBhNDVlOTgyZWY1N2FhYzE3YWU0YTZfbTFBcjRpaGxlVWNUVnBUNURTTVB5U0Z3VlFjWE53b3JfVG9rZW46VVNCemJ3QU9Jb0szU2d4TG5HamNBZTVHbnpiXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**集中式版本控制系统**（Centralized Version Control Systems，CVCS）有一个 **中央服务器**保存所有代码和历史记录。每个开发者只能从中央服务器下载最新代码，自己机器上只存工作区。

这样带来的问题就是，协作时需要依赖中央服务器，网络差或服务器宕机会严重影响效率。

因此，**分布式****版本控制系统**（Distributed Version Control System，DVCS）因而诞生。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NWMxNzdkMzE5NTNmMzU1NTY0ZTQwMDkyNTc3NzE4MTdfN2gySHJCWnFCa0ZEWmY2TFc0eFhSYVk2c2N1TmtBM1FfVG9rZW46WG4ycmIwU2FTb254dkh4blVjNGNHZW10blRnXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**分布式****版本控制系统**每个开发者的电脑里都有 **完整的仓库副本**（包含全部历史），而远程仓库只是“同步中心”，不是唯一来源。任何人都能恢复整个项目，并且分支、合并非常方便。

而**Git**就是世界上最流行的分布式版本控制系统。

## 2.2.背景

在 2005 年之前，Linux 内核社区的代码是依靠 **BitKeeper** 这个商业版本控制系统来管理的。BitKeeper 是当时少见的分布式版本控制工具，它帮助全球数千名开发者协同开发 Linux 内核。

但是，BitKeeper 并不是开源的。2005 年，Linux 社区和 BitKeeper 公司因为使用协议问题闹翻，BitKeeper 收回了对 Linux 社区的免费使用权。这对 Linux 内核开发团队来说，几乎是灭顶之灾：他们一夜之间失去了主要的协作工具。

就在这个关键时刻，**Linux 之父 Linus Torvalds** 决定亲自出手，重新开发一款新的版本控制系统。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MmU0YjZjY2Y5OTc3NTU0OTBkYWYwM2I1ZGExMWRhYjVfTTZ3ejVjcjNmVjY3QmRnS0FhQ3JkQ0dSY3g1cEQ4YXRfVG9rZW46TGVCTmJ0eGhib2ptOUZ4UWxDTmM4ZGE1bm4yXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

他为新系统设定了几个目标：

- **分布式**：每个人的电脑里都要有完整的历史记录，不能再依赖单点。
- **高性能**：要能快速处理 Linux 内核那样上百万行代码的大型项目。
- **强大的分支和合并**：支持全球范围的多人并行开发。
- **数据安全**：历史不能随便篡改，要有校验机制。

Linus 仅仅用了 **两周时间** 就完成了 Git 的雏形。 很快，Linux 内核社区全面转向使用 Git。凭借其分布式架构和极快的性能，Git 不仅完美解决了 Linux 社区的燃眉之急，还逐渐成为全球最流行的版本控制系统。

> 伟大的开源精神！

## 2.3.Github

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NTFjMmZkMDIwN2QwYzI1ZTRhYjRlMDhhZTE4YmRmMjJfN1FTanZPTXJxOWl4TU1YdVd2MVZkYmg4cFJDaE9uR05fVG9rZW46VGpnT2J3NVpsb0dWWlh4MmczU2NZMWZZbnBiXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

GitHub 是一个 **基于 Git 的托管平台**。它是一家网站/云平台，提供：

- 远程仓库存储（云端备份代码）；
- 协作功能（Issue、Pull Request、代码评审）；
- 社交属性（关注、点赞 Star、Fork 仓库）。

简而言之，Github是世界程序员的“朋友圈”。 

## 2.4.SSH Key

当你在本地用 Git 访问 GitHub 仓库时，GitHub 需要确认：

- 你是不是这个仓库的“合法主人”。
- 你有没有的权限。

**如果没有** **SSH** **Key**：

- 每次推送/拉取时，都要输入 GitHub 用户名 + 密码。
- 很麻烦，而且密码容易被截获（不安全）。

**有了** **SSH** **Key**：

- GitHub 用公钥来验证你本地的私钥。
- 一旦配对成功，以后推送/拉取都不需要再输入密码。
- 安全性更高（密钥加密通信）。

教程：[Github配置ssh key的步骤(大白话+包含原理解释)_github生成ssh key-CSDN博客](https://blog.csdn.net/weixin_42310154/article/details/118340458)

## 2.5.操作

> 此阶段较为基础，所以只列举了常见的6种git命令，想要更深入的学习git可以参考
>
> [黑马程序员Git全套教程，完整的git项目管理工具教程，一套精通git_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1MU4y1Y7h5?vd_source=f45d4b378e3632be8aa89f855fedf898&spm_id_from=333.788.videopod.episodes)
>
> 如果想要直观地学习，可以看看这个小游戏：[Learn Git Branching](https://learngitbranching.js.org/?locale=zh_CN)

仓库（Repository）就是 **Git 存放代码和历史记录的地方**。

1.**我们先在****Github****上创建一个远程仓库**：

**点击"+",选择New** **repository**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=N2Q1OWRjZDhhNzljNTA1NWQ3MDFjNWFiMWEzZjhmOWZfRTNGVDdNY05iTmZSQzRidHJpQzg4dkowVWFZUFNlcG1fVG9rZW46UXdUMmJtcUdMb2xJVzV4Y05UWGNBNnB2blFmXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

2.**填写远程仓库名称及其描述**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=ZmY1MjEzZTYzNDIyMTQwY2UyOWNjNWY0ZWI3YjUwZGZfOVdKSDQ2RzF0UU1FdXJXaktWbnF4ZVpkQjlIZTFxVlBfVG9rZW46THRwcWJpbzBWb0swRTh4b2lVV2M5alN4bldlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

点击Create repository,出现该页面的话就代表成功创建远程仓库：

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=YjJmNTRjMGQwNjU1YzFkYzAwMmQxN2ViYTczZDRkMmRfZndvckgzbUlKck5mU3ExOHhwakI4cmh2a05tUWZwS2JfVG9rZW46QU5ZRmJlb3Myb2huTHF4Tm4xQmNxMXRybmdlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

### 2.5.1.初始化本地仓库

> 我们在桌面建立一个名字为“Homework”的文件夹，然后在你的编辑器（vscode、webstorm）打开这个文件夹。

要让这个文件夹变成一个Git仓库，我们需要在终端输入该指令：

```Bash
git init
```

如果终端如图输出，说明你新建了一个 **隐藏的 .git 文件夹，以后在这个目录下写的代码，都能被 Git 管理！**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MjAzNDczNjdkZTU4MzI1M2RhMTYzOWMxMDYxMTIwYWFfcXdTRHYydHBaRlFhbWRIaVA3MkN5U1JFcE5yOUJOeWFfVG9rZW46WHF3MWJSM09Rb0NTRWV4ajZaaGM0eWtPbnVlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

### 2.5.2.添加文件到暂存区

> 在此，我们于该目录下创建一个名为“README.md”的markdown文件。

在终端输入该指令：

```Bash
git add README.md
```

通过运行该命令，你可以告诉 Git 哪些文件的修改应该包含在下一次提交（commit）中。

### 2.5.3.查看仓库状态

查看仓库状态是为了查看你有没有需要提交的文件。

在终端输入该指令：

```Bash
git status
```

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NmVmZDJhZDY3Mjc3ZTIxZDM1YzMwNThjNTdlNjJmOGNfWmdhbmpnTmdncnpPbkl3b09vemNxeDlkd2ZkTTBMQmlfVG9rZW46RFZ1bWJXRmZSb0F2RzZ4a1JhVGNLSTZ1bkplXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

> 如图，终端对我们作出了反馈：
>
> - **On branch** **master**👉 **当前所在分支是master。这是 Git 默认创建的主分支。**
> - **No commits yet**👉 你还没有做过任何提交（commit）。也就是说，目前仓库还没有“历史存档”。
> - **Changes to be committed**👉 这里显示的是 **已经被git add加入暂存区的文件**，等待下一次提交。
> - **new file: README.md**👉表示你新建了一个文件 README.md ，**Git 已经准备好把它提交到仓库**。
> - **Untracked files:**👉 这里显示的是 **还没被 Git 跟踪的文件**。*(**`.idea/`**是我用**Webstorm**生成的配置目录，目前还没被 Git 管理。如果使用Vscode是没有这个目录，请忽略)*

### 2.5.4.提交保存到**本地仓库**

在终端输入该指令，注意 -m " ",这里引号内的文本是你本次的提交消息。

```Bash
git commit -m "doc(init): add README.md"
```

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MDUwMjU2MGEyMTA3NzJiNzA2MmI4MDhiODQwMzYzOThfeWRFc2pKZVRJT0NnYm9oTUVmU0RzMkVzSHZhdEhUQVpfVG9rZW46RGVMSGJ1V0FYb3BvZ1h4aTI2VmMzSHc4bmtlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

> 如图，终端对我们作出了反馈：
>
> 1. **[master (root-commit) e471a48] doc(init): add README.md**
>    1. `master` → 当前分支名字（默认是 master）
>    2. `(root-commit)` → 表示这是仓库的**第一次提交**（根提交，没有父节点）
>    3. `e471a48` → 本次提交的哈希 ID（commit id，可以用它回溯到这次提交）
>    4. `doc(init): add README.md` → 提交信息：
>       - `doc` = 文档类型提交
>       - `(init)` = 表示这是初始化阶段的文档
>       - `add README.md` = 具体做了什么
>       -   ***doc(init): add README.md是一个非常符合commit规范的消息，目前暂时不要求掌握commit规范，我们会在第一次课程内涉及。***
>
>       - 
> 2. **1 file changed, 1 insertion(+)**
>    1. 一共改动了 **1 个文件**
>    2. 增加了 **1 行内容**（就是 README.md 的内容）
>    3. 
> 3. **create mode 100644 README.md**
>    1. `create mode` → 说明创建了一个新文件
>    2. `100644` → 文件权限（普通文件，可读写，不可执行）
>    3. `README.md` → 新建的文件名

### 2.5.5.推送提交到远程仓库

**git commit**只是把改动从 **暂存区** 保存到 **本地仓库**，形成一条历史记录。就像在自己电脑里存了个“存档”。

这一步完全发生在本地，GitHub 上什么都看不到。想要出现在 GitHub 页面上，我们需要推送到我们github上的远程仓库。

在终端输入该指令：

```Bash
git remote add origin git@github.com:你的用户名/你的仓库名
```

然后让我们的本地分支和远程分支建立连接，推送提交：

```Bash
git push -u origin master
```

但是，终端突然显示了一大段话：

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NzU1ZjY3ZDM5MmQ5ZGU1ZGVmYjM5NmQwZGY4YjJjY2NfbVl1WlRITEt1UG9OOU5JZUhSVlYwS3JRMnlOdnN6RTFfVG9rZW46TGlsMWJERFo3b2kwZHF4WnZhWmN2VFZvbnpoXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**这个提示非常正常，不用慌**。它的意思是：当你第一次用 **SSH** 连接 GitHub 时，Git 需要确认：

你连接的 github.com是不是“真的 GitHub”，而不是冒名顶替的假服务器。

它通过一个 **公钥****指纹（fingerprint）** 来验证。

所以 Git 问你：Are you sure you want to continue connecting (yes/no/[fingerprint])?

就是要你确认是否信任这个服务器。**我们直接输入yes,然后回车就行！**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=Zjc0ZmRhYjhkYzg1MWI2OWRkMThlODlkZWIwZDZlMzdfMTcwYlBTUlV3cUphRjFOMWJzd2NSZTc0T2x6d1pjSERfVG9rZW46QmpvUmJhckdRb0dpalR4eEZjamNZYThsbmxkXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

这样，我们就**第一次成功推送到** **GitHub****了！并且GitHub 的****公钥****被记住了，以后不会再问你一遍了。**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MWJiZTU3YjI1YTFkZjY5NjIwMjZkM2NjYzE4MzUxMGZfQ05QTzQ3eXBVczZtRkF3c0JTeUludGlDYzdscjRFdENfVG9rZW46QjRYWWJJTEJUb0t5NTJ4RU41VGNRcFlEbm9nXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**Github****也正常显示了！**

### 2.5.6.查看提交历史

在终端输入：

```Bash
git log
```

如图是我们的提交历史：

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=YWEwN2IxOWMxNTA5ODllODFhZTkzYmQ5MGZiMWRhNWFfMWFiSWRLRnpwZWdLcE5WZGNDbm92VEJ0TjBFczJDMkdfVG9rZW46UFpqbmIyOVJrb2pXN1p4MFpGaWNpemxrblRoXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

# 3.Github

从刚才的操作，我们不难发现**Github****对于我们每一个程序员非常重要**。

> **Github****是世界最大的代码托管平台，几乎所有知名的开源项目（Linux、Python、****React****、Vue、TensorFlow…）都托管在 GitHub 上。**
>
> **在找工作时，很多公司都会看应聘者的** **GitHub****。一个维护良好的 GitHub 主页 = 活的简历。它能直接展示你的实力，而不仅仅是简历上的一行字。**
>
> **企业内部用** **GitHub** **或 GitLab 来进行多人协作。代码托管、分支管理、****PR** **审核、****CI/CD** **自动化部署，一条龙解决。没有 GitHub（或类似平台），现代团队协作几乎不可能高效运行。**
>
> **GitHub****是开源运动的“大本营”。世界各地的开发者因为 GitHub，能够跨越国界、语言、时区，共同开发软件。**

以下内容介绍我们如何玩转Github：

## 3.1.⭐ Star

**Star，**收藏你喜欢的项目，就像给视频点个收藏。

> 收藏课件谢谢喵~

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NmEwN2Q3ZDU4YjIwYWU2NGE1MjlhNGJiZGM5MGYxM2RfZ3E0dXd1cXhGY1JyUnBOeUwySm5JU2x6d2RPYTlxdkZfVG9rZW46WmtYNmJVYXVEb3NyZVN4REhJTmNxQ0dQbkRoXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

Star数也是一个项目人气的象征。**它能直接展示你的实力！**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NTk2OTE2MGViOTA1ZWNhZDE4NTVjYzhmNjUxMzkzZjZfR1gxU0FvWVJLNW9wRWR1a282VjA3M3FXV3RQNTdrak5fVG9rZW46WXlZVWJXdVZpb2dhamR4OTRUYWN2U1RTblVlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

## 3.2.🍴 Fork

**Fork**, 复制别人的仓库到你自己的账号下。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=ODdmNzc4OWQzOTJkMmZmMTJiZmU2OGZjYmFkNThkN2ZfRWt1ZDBoUGRBeHFPeUdXTlc4SXJaSGdFd3pNU2lvUjlfVG9rZW46VEM1emI4Y1I1b1E5S1d4c1pIS2MzSVphblJkXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

这样，我们就得到了一份一模一样的仓库：forked from指示着原仓库。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=NGVjMzJjNGQ1ZDA5N2ViOWQ5MTQ5MzFjNzhiNDAwYjFfbGhyY1M3YVh3WnA4NFYxdGR5TlRaSU9WSkFyakZFMU5fVG9rZW46SUZQMWJZZEQyb1hGeGZ4NlhWeWNPdXYybjliXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

## 3.3.🖥️ Clone

fork只是把别人的仓库复制成自己的远程仓库，我们想要在本地改代码，就要使用**Clone把它变成自己的本地仓库**。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MzIwZWZlN2ViZjFjZTcxZGQ1YTQwMmQzMTcyOTcyNDlfMWw5U1B4ODBVaE5vTzBIRlBJeVVQUTBjUXMwYlpiUkhfVG9rZW46VU5SeWJ2cnhkb0ZIRXZ4TnA1R2NmRjg0blljXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

三种方式皆可以保存到我们本地:

1.**HTTPS** **/** **SSH** **/** **GitHub** **CLI** **——需要在命令行输入（自行了解****指令****）**

2.**GitHub** **Desktop——点几下就行，最推荐，后文会有详细介绍**

3.**Download** **ZIP**：**点一下就能下载压缩包，解压后直接用（不推荐，只适合只想看看代码、运行一下，不打算参与开发的人）**

## 3.4.📌 Issue

发现 Bug 或有新想法，可以**提Issue，这是和项目作者交流的主要渠道。**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MjU3NGJmZmM1NWRkMDEzNDZjY2FkNDY2YWI4YmJlZjZfMEoydXBHOUN0RmFDSXVwQjJ3VU9vd2lSMURwckF4ajFfVG9rZW46WEFDeGI2Rk1ub29ocnp4UkRPN2N6NjljbnViXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

## 3.5.👤 Follow  

Follow大牛，第一时间看到他们的新项目。从而获取学习资源、了解最新技术趋势。

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MWIzOThmMzc4OTYzOGRhNWZiOGNkYTY5ZTkwNjdjYTRfTjZURFdKdTZqanJYVTVwM0hJSjBIV0xpTnV6QlA2NVlfVG9rZW46SzhZWmJwdVdWb1NNUU94ZVdJd2NsMUVsblJnXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**关注蓝山谢谢喵~**

# 4.Github Desktop

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=YzE4MmZiYjUyYzZkYzQ3ODdlOTNjNmE2NTkyYTBiZGJfVHc1ZFljeXZlM2hJc0JWcWlGWFo0cFpoYmhFSW5IN0hfVG9rZW46R01mWWJKemtYb0h1S3F4SHR2V2NpWmZMbkJoXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

GitHub Desktop 是 GitHub 官方出的 **图形化 Git 工具**。 在第二章的时候，我们用Git 都要敲命令，GitHub Desktop直接把这些命令做成了按钮和界面，让你直接**点一点**就能完成。

> 其实无论是VsCode或者是IDE，内部也自带图形化Git工具，建议自行下来学习了解。

## 4.1.安装

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2JjMzUyNTgyMzcwMmNhMGVjMTBjMGZhZDliODNkMWJfYUNkeGtqYnZ6YUhnbWIxdGo3Uk96TUhWSnNZWnB0NkpfVG9rZW46WjkyemJFd0w3bzRrT0p4N1ZSemNvZ3l4bkd6XzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

去官网[github.com](https://github.com/apps/desktop)下载并安装，打开后，登录你的账号。

## 4.2.获取仓库

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=M2IzNGFhNGVhMDQ0OTQ5YjcyY2FiNmIxODZmMDQzZmZfcHlFRlBjV25kN29yRk9FVkJSOFlhNHpZd0t3Nk16N1VfVG9rZW46WGRhbmIzU2NCb1JyR2F4ejZDbmNSdXd0bjhiXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

这里给我们提供了三种选项：

### **4.2.1.****Clone** **Repository**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=ODg1YmRkY2NjMmU0NGE4Yjc1YmUxNTQ2MWM2MTliZDFfOVBucFdjSUNxd0lWbUxOWVdxSVZ3RGNrdjJvbE5WVjdfVG9rZW46V1hKaWIxWDJLb0VYcVd4SVVpUGNWQkUxbk9oXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

**GitHub.com:**你与你组织下的仓库，都是这里, 在下方选中点一下就能克隆。

**URL**：在GitHub上，找到其他人的你想要的仓库，点**Code → 复制仓库地址（****HTTPS****/****SSH****）→** 粘贴地址 → 选择本地保存路径 → Clone。

### 4.2.2.Create New Repository

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=Yzg4N2JjZjNhMjA3YjM2Zjg4ODdmODJkODU5OWFmZTlfM2EwSnlKUWF6SG42TXpqUW5vUXlwZFYwQnVpYXJ5c1VfVG9rZW46WFlUeWJvNm1jb1hucHB4bkZ4V2NuZFlBbm9oXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

填写信息，创建后，可以点 **Publish** **repository** 上传到 GitHub。

### 4.2.3.Add Local Repository

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=MmVjNGJlNDc3YjVhN2Q2OWQyNDI2ZDNjNDRhY2ZlOWNfWlEwcDdTbmhUZmdyWVJQZUVnaXc5VEUxT3hLUWJMbmVfVG9rZW46SzhDbWJWV3pvb1Z3S1F4TnRHS2N5Q21ubnVjXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

如果你本地已经有一个 Git 仓库，选中目录即可。

## 4.3提交和推送

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=YTRjMTJkODIwZjE2Y2JhNTBkZjcxOWVjNjAwYjUxYTFfazIwWjVLOEdjVlI1b3hLSmlGekFpTkxEMTZ2TUdIdkpfVG9rZW46R3BwamI1bmZQb2o5MEV4M3FEQWNFT0tIblJlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

修改文件后，GitHub Desktop 会自动显示**改动的文件**。（右侧黄色是改动文件，绿色是新增文件，红色是删除文件）点文件可以预览改动。

在左下角写 **Summary（必填）** 和 **Description（可选）之后，点击下方Commit就可以提交到当前分支。**

![img](https://lanshanteam.feishu.cn/space/api/box/stream/download/asynccode/?code=Y2VhM2Q3YjkzOWIyNjgxZWI4ZjFlY2FiNjhmMDU3OTVfMnJyTXlyU2tVV3hIS25za0c1eEdrZEpVTTE1dzJ5TkdfVG9rZW46QlVoN2JOeTFUb0IxSEl4Y095WGNBMmxGblZlXzE3NTg0NTY4MTE6MTc1ODQ2MDQxMV9WNA)

提交后，点击上方的 **Push origin**，就可以把本地代码推送到 GitHub。

# 5.小作业

又到了激动人心的小作业环节了，为了体现你的学以致用，我已经把作业发布到了课件仓库里了。

请结合本课学习内容，克隆课件仓库到本地，并查看完成其中的作业。

前四名完成作业的仍会获得奶茶奖励。