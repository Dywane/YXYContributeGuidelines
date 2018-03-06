# YXYContributeGuidelines

# How to contribute

首先了解一下一些重要的资源：

* [项目的代码规范](https://gitlab.com/Dywane/NewYouXiaoYun/blob/master/CodingGuide.md)
* [项目Worktile]()
* [问题、反馈](https://gitlab.com/Dywane/NewYouXiaoYun/issues)
* [后台接口]()

## 如何提交一个commit
在优校云中，我们使用代码评审机制，即developer可以在属于自己的分支上进行开发，当功能完成后，可以将自己的分支合并到主干，这时需要提交一个**“合并请求”（merge request)**，并由owner对该分支进行代码审查，确保代码质量。

#### merge request
1. developer通过develop/master/feature_xx.xx（分支视情况而定）创建自己的分支进行开发，如发发创建 YXY_testDemo分支
2. developer进行开发，并把commit push到自己的分支的远端仓库分支
3. 当完成了一个功能点的开发之后，登录[Gitlab网页-MergeRequest](https://gitlab.com/Dywane/NewYouXiaoYun/merge_requests)进行合并请求（**注意所有的合并代码请求都在网页进行**，不要在本地进行，因为你合并不上去）
4. 在网页中选择新建合并请求
![](https://i.loli.net/2018/03/06/5a9e0b2eac4aa.png)

![](https://i.loli.net/2018/03/06/5a9e0b340b040.png)
5. 设置对应数据并填写文档
![](https://i.loli.net/2018/03/06/5a9e0b3660bd0.png)
6. 如果代码存在问题，返回给developer修改后再重新发起merge request即可
7. 如果代码没有问题，则owner完成合并请求

#### conflicts
如果在合并中产生了冲突的解决方案：

1. local_master 更新到最新代码（remote_master）
2. local_master 合并到local_dev，肯定会产生冲突<注意不是local_dev 合并到local_master，和gitlab网站操作其实刚好是反过来的>
3. 解决好local_dev冲突后，push 代码到 remote_dev
4. 最后通知下owner已经解决好冲突

#### log message
log message应该清晰扩要，如果是小的改动，如：修改了一个bug，字体调整等，可以使用简单的一行说明文字即可，但是如果是新功能的添加、大量改动、宏定义的增添、删除、修改等，则需要详细的log message，必要时可以附带markdown文件进行解释

#### git commit message
* 使用**Update**表示某个功能的更新
* 使用**Fix**表示某个Bug的修复
* 使用**Feat**表示某个新功能的完全完成
* 使用**Add**表示添加了新的文件、功能、函数、变量
* 使用**Remove**表示移除了某些文件、功能、函数、变量
* 使用**Pod**表示添加了某个第三方库，并需要在log message中附带该第三方库的地址
* 使用**TODO**表示某个功能需要在下一个commit中完成

#### 关联worktile任务与git commit
如果某个commit是对某个在worktile上面的任务的完成，在commit的时候应该加上worktile上对应某个人物的任务编号，描述中应该加上**#任务编号（例如：#123）**，提交记录会被自动关联到相关任务上。任务编号可以在worktile对应任务的任务详情里右下角找到。

#### merge request message 模版

> ### Description of the Change
>  (这次MR距离上一次所进行的全部修改）
> ### Known issue
>  (这次MR是否包含某些问题，会影响到自己模块或其他人模块的使用)
> ### Fix bugs
>  (这次MR修复的Bugs，同时如果是在Issue中的bug需要在对应Issue中添加相关文档，并关闭Issue）

## Issue
如果在开发过程中遇到需要**讨论、多人协同解决、其他人模块问题导致自己开发上出现问题**的情况，可以提交一个Issue。Issue功能的优秀之处在于解决方法以文字形式记录下来，并可以以邮件通知每一位参与者，所以我推荐就算在口头上讨论出来的解决方式，最后也将其归档到Issue中，以文本形式记录下来。

#### before submitting an issue
1. 先更新到最新版本，查看其他人是否已经修复了该问题
2. 查看Issue页面是否有其他人已经报告了该问题
3. 联系相关人员进行修复

#### how to submit a good issue
* 清晰的问题描述：xxx模块的xxx函数需要进行xxx调整
* 如何重现某个问题：xxx操作下xxx模块会发生内存泄漏、崩溃
* 提供实例：xxx函数返回值需要添加xxx参数，字典格式应该如xxx
* 阐述进行修改的原因：xxx模块中显示需要xxx，需要xxx模块进行返回
