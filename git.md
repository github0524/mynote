## git 

[(120条消息) 20 个最常用的 Git 命令_git常用命令_万物不及香香的博客-CSDN博客](https://blog.csdn.net/qq_53113396/article/details/124983800?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-124983800-blog-45847439.235^v36^pc_relevant_anti_vip_base&spm=1001.2101.3001.4242.2&utm_relevant_index=4)

git init //把本文件夹设置成git文件夹

git clone github上的url

### 更新服务器分支上的内容到本地

```python
git pull origin master
```

### 更新本地文件到服务器

注意几个概念：工作区-----暂存区（本地）----远程仓库

git add选择添加哪些到暂存区，git commit 启动添加

svn add ------------git add

svn commit --------git add、git commit(两个都要有)



如果对本地文件有了修改，则需要对仓库文件进行更新，比如本地文件中删除了一个文件。 下面将显示如何对仓库更新。

首先进入你的master文件夹下，右键打开“Git Bash Here” ，弹出命令窗口 ，输入如下内容

输入 以下文本即可更新仓库

git status

git add -A

git commit -a -m "update" ： 能提交修改过，但是没有添加到缓存区的文件（修改过的就能提交）

git push origin master -f

### 提交部分代码

方法一：git add 提交的文件和文件夹（tab键可提示）

git commit -m ""

git push origin master

**方法二：直接使用commit 提交**（推荐）

**git commit  <file>  -m "your comment"**

**git push origin master**

方法三：这种会短暂消失一写忽略的修改，不建议

git add demo.html // 提交到暂存区
git stash -u -k  // 忽略其他修改，关键一步
git commit -m '修改演示文件' // 提交暂存区
git pull // 拉取合并
git push origin master // 推到远程仓库
git stash pop // 恢复之前忽略的文件（非常重要的一步）



### 显示哪些纳入版本

git ls-files（中文显示不了）



### git commit

在使用Git进行版本控制时，git commit命令是非常重要的一个操作，用于将工作区的修改提交到本地仓库中。下面是git commit命令的一些常用选项：

1. -m "message"：指定提交的信息，message为提交信息的内容。

例如：

```
Copy Codegit commit -m "Add a new feature"
```

1. -a：自动将所有已经被Git跟踪过的文件进行提交，不需要手动执行git add。

例如：

```
Copy Codegit commit -a -m "Update some files"
```

1. -n：不自动打开编辑器进行信息编辑，而是直接采用命令行方式输入提交信息。

例如：

```
Copy Codegit commit -n -m "Fix a bug in the code"
```

1. -v：在提交信息前，先打印出所有与提交相关的文件的差异信息。

例如：

```
Copy Codegit commit -v -m "Refactor some code"
```

1. --amend：修改上一次提交的信息或者撤销上一次提交，并重新进行一个新的提交。

例如：

```
Copy Codegit commit --amend -m "Fixed the issue with the new feature"
```

1. -S：添加数字签名，以保护代码的完整性和真实性。

例如：

```
Copy Codegit commit -S -m "Merge branch with master"
```
