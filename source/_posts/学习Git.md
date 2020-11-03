---
title: 学习Git
date: 2020-05-28 20:46:26
tags: 随笔
top: 11
---


# Git总结
 <!-- more-->
## Git下载网址： 

 **[Git官网](https://git-scm.com/downloads)**

 **[Git下载国内镜像网址](https://github.com/waylau/git-for-win)**
 
## Git设置用户名和邮箱
` git config --global user.name "you github name" ` //填写你的github用户名

` git config --global user.email "you github email" ` //填写你的github邮箱

*注意：git config --global参数，有了这个参数，表示你这台机器上所有的GIt仓库都会使用这个配置，当然你也可以对某个仓库指定不同的用户名和邮箱。*

1. github.com 很难访问到的解决方案

 DNS解析   ---->  github.com 

 搜索 windows10(c) Windows / System32 / drivers / etc / hosts文件 

 140.82.113.4 github.com 

## Git常见命令

**当前分支下操作的命令**

2. git日常操作 （日常工作流）

   - `git init` (初始化一个仓库,通过git init 把该目录变成git可以管理的仓库)

   - `git add index.html`(将需要的东西放入暂存区中)

   - git commit  (将暂存区的东西形成一个版本)

**(练习一下)**

*npm init 初始化*

*npm add express* （添加node_modules）

3. `git status`   （查看暂存区，可以查看是否还有修改的文件未提交）

4. git rm -r --cached ./node_modules/   把node_modules移出暂存区（不需要这个）

5. `git commit -m "安装依赖"` （该命令告诉Git，把文件提交到仓库，双引号内是提交时注释内容）

6. 创建 .gitignore 文件 输入 node_modules/ -->表示node_modules文件下的东西不要。（node_modules的文件夹边灰） 
   - 可以利用到在项目中不用上传的东西（比如node_modules 还有编译器的东西等）

7. git checkout -- index.html (撤销命令) *了解一下*
    - 表示：当我们修改了index.html文件(如：给index.html加个p标签) 然后git status 可以查看到 index.html被修改。需要上传(git add命令)

    - 如果我们不需要修改的内容。可以撤销上次的修改(git checkout -- index.html)

8. git log (查看提交了多少个版本 从新->老)
    - [扩展] 可以使用git log 内置样式 把它输出一行 (git log --pretty=oneline) 比较容易观看
    
    - 可以查看到 前面一大串数字英文（16进制的40位）是sha-1加密运算法 相当于唯一key 可以利用这个唯一key来回退版本

9. 实现版本回退 *不太推荐使用* *适用于本地*
    - `git reset --hard HEAD^`  (git reset --hard HEAD^^   回退2个版本)
    那如果要回退到前50个版本呢，使用上面的方法肯定不方便，我们可以使用下面的简单命令操作即可:
    `git reset --hard HEAD~100`

    - git reflog 查看历史迁移的过程（提供了唯一key的前7位）
    - git reset --hard 7d55862(利用唯一key)  版本跳转

10. 查看历史记录信息

    `git log`

11. git revert HEAD  (多了一个版本)

    git revert 2e20eaa (可能会产生版本冲突)

    取消版本回退 git revert --abort

12. 查找工作区与暂存区的差异 git diff
    - 比较工作区和本地版本库中最近一次commit的内容 git diff HEAD
    - 比较暂存区与本地版本库中上一次的内容 git diff --cached
    - git diff "xxx" "xxx" （比较两个版本的差异 可以利用唯一Key）

**多分支操作**

13. 
```
    git branch dev   (创建一个新的分支 dev)

    git checkout dev （切换到 dev分支下)

    git checkout -b dev （创建一个dev分支并切换到该分支,相当于上面2条命令）

    git branch  （查看当前分支,会列出所有分支，当前分支前面会加一个星号）
```
**(练习一下)** 在dev分支的index.html中添加一段“我是dev分支内容”.上传到commit 。然后切换到master分支看不到内容。在dev分支可以查看到内容。

14. `git merge dev`    （合并分支） 

    *合并之后 选择想要的内容。再上传到commit*

    利用 git log --graph --pretty=oneline查看分支的由来

15. git branch -d dev1(删除dev1分支)

16. git stash 存入栈当中
    
    git stash pop 吐出来 （会告诉你添加还是xxx）

**与github连接使用**

17. git remote add origin git@github.com:LinRude/gitdemo1.git
    创建一个关联的远程仓库(起名origin)

18. 进行用户设置 git config --global user.email   git config --global user.name

19. 连接服务 ssh-keygen 创建完后 C->用户->Administrator->.ssh -> id_rsa.pub 复制里面内容到github 里设置SSH and GPG keys 设置密钥

20. 提交到远程仓库里面 git push origin master

21. git pull origin master 拉取主分支的内容 （先切换到dev分支）

22. git clone + 项目Git地址（使用命令克隆一个本地库）


## 总结创建与合并分支命令如下：
(1)查看分支： `git branch`

(2)创建分支：`git branch name`

(3)切换分支： `git checkout name`

(4)创建+切换分支： `git checkout -b name`

(5)合并某分支到当前分支： `git merge name`

(6)删除分支： `git branch -d name`