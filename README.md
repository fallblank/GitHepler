# GitHepler
这是Git的学习手册，好久以前就开始使用git，但仅限于会使用一些简单的命令，如init、
add、commit、push等。一直想好好弄清楚git，今天终于开始了（这执行力真是低，╮(╯▽╰)╭，改！改！改！）。我打算就在这个README上完成所以的操作吧！同时记录下想要的内容，方便以后查看。</br>

## Git基础:
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
