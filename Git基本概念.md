# Git 基本概念

[Github官方最好的参考资料](https://try.github.io/)

[Git速查手册](https://github.github.com/training-kit/downloads/zh_CN/github-git-cheat-sheet/)

[Git互动学习网站](https://learngitbranching.js.org/)

## Git 能做什么？

### Git 能保存每一次的修改

Git 是款分布式版本控制软件。

想象一下，当你开始写笔记时，如果你想保存每一次的修改，一开始的文件是这样的

```
笔记0501
```

在数个月后，文件变成了

```
笔记0501
...
笔记0701男朋友修改
笔记07012女朋友删除男朋友修改
```

使用 Git 可以让文件一直是这样的

```
笔记
```

谁，什么时间，修改了什么内容，全部都由Git在后台处理好了，而你只需要几个简单的命令就可以看到或者回退到某个版本。

Git 管理的文件的全体就是仓库 (repository)

> Git 负责管理文件的各个版本，能够让你回退到 Git 快照过的每一个版本。

### Git 能非常简单的多人协作

假设一份笔记，今天我改一下，明天你改一下，文件会不会被改的面目全非？

每次改完文件后，还得传来传去怎么麻烦？

现在，你可以在Github上创建一个私人仓库，几个人就可以一起维护一个仓库，而Git则会负责保持文件不会有任何破坏或冲突。

### Git 能在没网络的环境下工作

学生党经常带着电脑四处搞游击，网络糟糕的条件下，Git可以让你在本地进行正常的工作，在有网络的时候进行同步。

**以下是第一次学不需要搞懂的内容**

##  TODO  怎么安装Git？



## 怎么调教Git，让它十分顺手？

### 使用 VSCode 作为Git的编辑器

[参考官方文档](https://code.visualstudio.com/docs/editor/versioncontrol#_git-patchdiff-mode)

1. 在命令行运行 `git config --global core.editor "code --wait"`
2. `git config --global -e`  命令在VSCode中修改配置文件
3. 增加行
   ```cfg
    [diff]
    tool = default-difftool
    [difftool "default-difftool"]
    cmd = code --wait --diff $LOCAL $REMOTE
   ```

于是对于以下命令就可以用 VSCode 来操作

1. `git rebase HEAD~3 -i` do interactive rebase using VS Code
2. `git commit` use VS Code for the commit message
3. `git add -p` followed by e for interactive add
4. `git difftool <commit>^ <commit>` use VS Code as the diff editor for changes