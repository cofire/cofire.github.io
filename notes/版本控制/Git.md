# 存储库创建

链接：https://github.com/

点击创建即可

# 存储库克隆

~~~
git clone git@github.com:cofire/hello-world.git
~~~

# 分支操作

~~~
# 查看本地分支
git branch
# 查看所有分支
git branch -a
# 查看远程分支
git branch -r
# 拉取远程分支并创建本地分支
git checkout -b 本地分支名 x origin / 远程分支名 x
# 分支切换
git checkout 分支名
# 创建本地分支 dev
git branch -b dev
# 将本地分支推到远程分支（只会将切换出内容上传，其余需要手动上传）
git push origin dev
# 删除本地分支
git branch -d 分支名
# 删除远程分支（少用）
git branch -r -d origin/分支名
~~~

# git使用流程及规范

- 尽量不碰master分支
- 代码拉取开发分支
- 然后将分支复制一个任务分支
- 然后将任务分支合并到开发分支

~~~
# 克隆代码
git clone git@github.com:cofire/hello-world.git
# 拉取远程分支
git checkout -b dev origin/dev
# 复制当前开发分支
git checkout -b dev-0823
# 代码修改
# 切回原分支
git checkout dev
# dev 分支更新
git pull origin dev
# 比较两个分支
git diff dev-0823
# 分支合并
git merge dev-0823
# 解决冲突
# add
git add .
# commit
git commit -m "修改内容"
# push
git push origin dev
~~~

# 参考链接

- https://backlog.com/git-tutorial/cn/intro/intro1_1.html