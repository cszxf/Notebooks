# 添加提交
```bash
git add .
git commit -m "xxx"
git push
```
# 从本地创建仓库并上传
简易的命令行入门教程:
Git 全局设置:
```bash
git config --global user.name "ConanSteve"
git config --global user.email "270523124@qq.com"
```
创建 git 仓库:
```bash
mkdir gittest
cd gittest
git init
touch README.md
git add README.md
git commit -m "first commit"
git remote add origin git@gitee.com:conansteve/gittest.git
git push -u origin master
```
已有仓库?
```bash
cd existing_git_repo
git remote add origin git@gitee.com:conansteve/gittest.git
git push -u origin master
```
以后可以直接 `git push`当前分支到远端
# stash 暂存
1. **git stash save "save message"**  : 执行存储时，添加备注，方便查找，只有git stash 也要可以的，但查找时不方便识别。
2. **git stash list**  ：查看stash了哪些存储
3. git stash show ：显示做了哪些改动，默认show第一个存储,如果要显示其他存贮，后面加stash@{$num}，比如第二个 git stash show stash@{1}
4. git stash show -p : 显示第一个存储的改动，如果想显示其他存存储，命令：git stash show  stash@{$num}  -p ，比如第二个：git stash show  stash@{1}  -p
5. git stash apply :应用某个存储,但不会把存储从存储列表中删除，默认使用第一个存储,即stash@{0}，如果要使用其他个，git stash apply stash@{$num} ， 比如第二个
6. **git stash pop** ：命令恢复之前缓存的工作目录，将缓存堆栈中的对应stash删除，并将对应修改应用到当前的工作目录下,默认为第一个stash,即stash@{0}，如果要应用并删除其他stash，命令：git stash pop stash@{$num} ，比如应用并删除第二个：git stash pop stash@{1}
7. git stash drop stash@{$num} ：丢弃stash@{$num}存储，从列表中删除这个存储
8. git stash clear ：删除所有缓存的stash

```bash
git stash save "xxx"
git checkout BRANCH_NAME
//do ...
```
# 疑难杂症
## git error: remote origin already exists.
解决方案
1. 先删除远程 Git 仓库
`$ git remote rm origin`
2. 再添加远程 Git 仓库
`git remote add origin xxx`（xxx是克隆地址）


# 参考文献
1. [git本地仓库关联远程仓库的方法](https://segmentfault.com/a/1190000012081004)
2. [合并本地仓库与远程仓库](https://www.cnblogs.com/MrSaver/p/12127996.html)
3. [git 使用强制本地仓库和远程仓库合并](https://blog.csdn.net/qq_32035241/article/details/105013510)
4. [git 查看所有远程分支以及同步](https://www.jianshu.com/p/5adc552323ca)  