# Git 的进阶用法

## Git 钩子

在仓库的隐蔽文件夹 `.git/hooks` 中存放着很多钩子的示例， 可以查阅[官方文档](https://git-scm.com/book/zh/v2/%E8%87%AA%E5%AE%9A%E4%B9%89-Git-Git-%E9%92%A9%E5%AD%90)， 看看钩子的定义。

钩子文件本质上是 Shell 脚本。

### 示例

每次提交前把目录下的文件复制到OneDrive中。

1. 重命名 `pre-commit.sample` 为 `pre-commit`
2. 删掉除第一行外的所有代码
3. 加入命令 `cp /path/to/file ~/OneDrive/` 即可

`cp` 有很多选项可以选择， 一般用 `-rfu` 表示包含子目录，强制复制，只复制更新的文件。