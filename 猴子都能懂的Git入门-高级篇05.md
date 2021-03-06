#### 猴子都能懂的Git入门-高级篇

2019年6月17日

天气：晴

##### 五、改写提交

(这些属于比较高级的技巧，平时用的不多)

##### 1、修改最近的提交

指定amend选项执行提交的话，可以修改同一个分支最近的提交内容和注解。

使用场合：

- 添加最近提交时漏掉的档案
- 修改最近提交的注解

##### 2、取消过去的提交

使用revert可以取消指定的提交内容。使用rebase -i或reset也可以删除提交。但是不能随便删除已经发布的提交，这时需要通过revert创建要否定的提交。

使用场合：

- 安全地取消过去发布的提交

##### 3、遗弃提交

使用reset可以遗弃不再使用的提交。执行遗弃时，需要根据影响的范围而指定不同的模式，可以指定是否复原索引或工作树的内容。 

除了默认的mixed模式，还有soft和hard模式。欲了解受各模式影响的部分，请参照下面的表格。 

| 模式名称 | HEAD的位置 | 索引   | 工作树 |
| -------- | ---------- | ------ | ------ |
| soft     | 修改       | 不修改 | 不修改 |
| mixed    | 修改       | 修改   | 不修改 |
| hard     | 修改       | 修改   | 修改   |

主要使用场合：

- 复原修改过的索引的状态(mixed)
- 彻底取消最近的提交(hard)
- 只取消提交(soft)

##### 4、提取提交

使用cherry-pick，您可以从其他分支复制指定的提交，然后导入到现在的分支。 

![pic42](G:\Github projects\OnlyForLearnGit\picInFile\pic42.PNG)

使用场景：

- 把弄错分支的提交移动到正确的地方
- 把其他分支的提交添加到现在的分支

##### 5、改写提交的历史记录

在rebase指定i选项，您可以改写、替换、删除或合并提交。 

使用场景：

- 在push之前，重新输入正确的提交注解
- 清楚地汇合内容含义相同的提交。
- 添加最近提交时漏掉的档案

##### 6、汇合分支上的提交，然后一同合并到分支

merge的特殊选项：squash

用这个选项指定分支的合并，就可以把所有汇合的提交添加到分支上。

![pic43](G:\Github projects\OnlyForLearnGit\picInFile\pic43.PNG)

使用场景：

汇合主题分支的提交，然后合并提交到目标分支。 

##### 7、实际使用案例

参考：https://backlog.com/git-tutorial/cn/stepup/stepup7_1.html

