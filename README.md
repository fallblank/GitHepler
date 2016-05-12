# GitHepler
这是Git的学习手册，好久以前就开始使用git，但仅限于会使用一些简单的命令，如init、
add、commit、push等。一直想好好弄清楚git，今天终于开始了（这执行力真是低，╮(╯▽╰)╭，改！改！改！）。我打算就在这个README上完成所以的操作吧！同时记录下想要的内容，方便以后查看。</br>

## Git单机篇:
- 创建Git仓库：git init
- 提交修改到缓冲区：git add \<file\>
- 提交到git仓库：git commot -m "description"
- 查看当前状态：git status</br>
这条命令会在实际中频繁使用，它能查看到你在git的工作区的各种操作，比如增加/删除/修改等
- 查看修改差异：git diff \<file\>
- 查看已提交版本：git log</br>
为了方便查看版本信息，有一些常用的修饰符：--graph，图像化的方式显示版本迭代路线；--pretty=oneline 一行显示；--abbrev-commit仅显示commit信息......
- 版本回退：git reset --hard \<版本号\></br>
HEAD表示当前分支的最新版，HEAD^表示前一版本，HEAD^^表示前两个版本，以此内推。HEAD～（n）前n个版本。更一般的方法是用版本散列值。
- 操作日志：git reflog</br>
git reset --hard \<版本号\>后，用git log不会显示回退版本后的信息，需要用git reflog去找回。
- 撤销修改，但未提交缓存区：git checkout -- \<file\>
- 撤销修改，提交到缓存区但没commit：git reset HEAD \<file\>
- 撤销修改，commit但未push到远程库：版本回退。
- 撤销修改，已push到远程库：GG，祈祷没捅娄子吧！
- 删除：git rm \<file\>
- 误删除：git checkout --\<file\>

## Git联机篇：
Git与GitHub搭配食用更佳哟！<br>
这里主要讲如何讲已有的本地git托管到github，或者从github开始一项工作。

- 将本地项目托管到GitHub<br>
在GitHub上新建一个空白的仓库，然后记下复制下地址（HTTP or SSH），然后本地添加远程仓库地址。</br>
1.git remote add origin \<address\></br>
2.git pull origin master<br>
3.git push orgin master</br>
这里默认远程仓库叫origin，pull和push都对master分支操作。</br>

- 从GitHub开始一项工作
先在GitHub上建好仓库，然后clone到本地，接着进行项目操作，最后push到GitHub。</br>
1.git clone \<address\><br>
2.git push origin master</br>
默认remote地址是指定好的。

## Git高级篇
主要关于分支管理，包括分支创建、合并、删除、冲突，多人协助以及分支策略。</br>
- 分支创建:git branch \<name\>
- 切换分支：git checkout \<name\>
- 创建和切换：git checkout -b \<name\>
- 分支查看：git branch
- 分支删除: git branch -d \<name\>
- 分支合并：git merge [optioal arg] \<name\></br>
分支的合并默认是采用first-forward策略，这只能在只有被合并分支做出修改，而合并分支没有修改的情况。如果两个分支都有修改就要进行手动解决冲突。还有就是first-forward会丢失分支信息，对于很小的信息修改采用这种方法。更一般的是使用修饰符：--no-ff -m "commit description" 这会进行一次commit操作。</br>
