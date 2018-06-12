# gitflowtest
this is just for git flow test

2.1 切换到本地仓库工作区

cd /home/timerhunter/workspace
1
2.2 从远程仓库克隆代码到本地仓库

$git clone https://xxxx@localhost:8443/r/valve/V5-Lora.$git
1
2.3 基于master分支，创建develop分支

/* 切换到master分支 */
$git checkout master
/* 基于master分支克隆develop分支，并在克隆完毕后直接跳转到develop分支 */
$git checkout -b develop
/* 推送develop分支到远程仓库 */
$git push origin develop
1
2
3
4
5
6
注：编码工作主要在develop分支，master分支主要用来发布稳定版本

2.4 在本地仓库的开发流程

完成一个功能点或者一天的工作结束时，将代码提交到本地仓库

/* 提交修改到缓冲区 */
$git add .
/* 提交修改到本地仓库 */
/* 如果是修复的BUG，应该在修改说明的最开始添加Bug#ID，多个Bug用逗号分隔，例如Bug#002,003 */
/* 如果是完成了一个指派的任务，应该在修改说明的最开始添加Task#TaskID,例如Task#165 */
$git commit -m "Bug#123 修改说明"
/* 每完成一个功能点可以对代码进行打包 */
$git tag -m "简要说明增加/修复/删除了什么功能" v0.0.0.170718
1
2
3
4
5
6
7
8
注：不是每一个Tag都需要提交到远程仓库，比如可以在完成一个功能点的编码工作后未编译就打一个包，仅存储于本地仓库，在编译成功&测试通过后，再打一个新的Tag包（里程碑Tag包），仅将里程碑Tag包推送到远程仓库

2.5 推送代码到远程仓库

当完成一个功能点或阶段工作时，将代码推送到远程仓库develop分支

/* 执行代码拉取操作，防止代码冲突 */
$git pull
/* 解决代码冲突后，推送代码到远程仓库*/
$git push origin develop
1
2
3
4
注：禁止将未编译或编译不通过的代码提交到远程仓库，如果编码工作进行未完成可以提交到本地仓库中，等待该功能点全部实现后再将代码推送到远程仓库中。