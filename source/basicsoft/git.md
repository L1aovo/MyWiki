# Git

commit 提交，将本地文件和版本信息保存到本地仓库

push 推送，将本地文件和版本信息推送到远程仓库

pull 拉取，从远程仓库文件和版本信息下载到本地仓库

![image-20230509130953530](https://cdn.jsdelivr.net/gh/L1aovo/blogpic@main/img/image-20230509130953530.png)

## Git常用命令

### Git 全局设置

```sh
git config --global user.name "L1ao"
git config --global user.email "L1ao@qq.com"

git config --list
```

获取仓库

```sh
git init
git clone xxx
```

### Git工作区中文件的状态

- untracked 未跟踪
- tracked 已跟踪

1. unmodified 未修改
2. modified 已修改
3. staged 已暂存

```sh
git status
```

### Git本地仓库常用命令

```sh
git status	查看文件状态
git add		将文件修改加到暂存区
git rm		删除文件
git reset	取消暂存或切换版本 git reset xxx.java | git reset --hard commit版本唯一标识符
git commit 	将占村区的文件提交到版本库 git commit -m "first commit" *

git log		查看日志
```

### Git远程仓库操作

```sh
git remote		查看远程仓库
git remote add	添加远程仓库
git clone		从远程仓库克隆
git pull		从远程仓库拉取 --allow-unrelated-histories 解决合并不同仓库未关联问题
git push		推送到远程仓库
```

Git提交代码

```sh
echo "# reggie" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/L1aovo/reggie.git
git push -u origin main
```

```sh
git remote add origin https://github.com/L1aovo/reggie.git
git branch -M main
git push -u origin main
```

Git拉取代码

```sh
git pull origin main 
```

### Git分支操作

```sh
git branch					查看分支
git branch [name]			创建分支
git checkout [name]			切换分支
git push [shortName][name]	推送至远程仓库分支
git merge [name]			合并分支
```

不同分支可以有不同代码，可以在不同分支下创建文件，然后合并看效果

合并时如果两个分支都有修改莫部分代码，可能会发生冲突

commit记录如何合理删除？

在合并时只提交指定文件报错可以加`-i`

### Git标签操作

```sh
git tag							查看标签
git tag [name]					创建标签
git push [shortName] [name]		推送标签
git checkout -b [branch] [name]	检出标签
```

标签打好就不会变了，静态

而分支是动态的