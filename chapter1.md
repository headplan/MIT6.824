# 课程简介

### 6.824 是一门什么课

6.824 是MIT开设的一门讲解分布式系统的课程 . 课程内容包括Golang语言的学习、分布式系统研究的动机、一致性协议算法、著名分布式系统软件论文讲解和一致性算法实现实验 . 这门课是一门实践性质比较强的课程 .

6.824 要求有一定的基础 , 先修课程包括6.033\(Computer System Engineering\)和6.004\(Computation Structures\) , 即要求学生对操作系统 , 计算机网络 , 计算机体系结构有一定的了解 .

> 6.033 - [http://web.mit.edu/6.033/www/](http://web.mit.edu/6.033/www/)
>
> 6.004 - [https://6004.mit.edu/web/spring21/](https://6004.mit.edu/web/spring21/)

#### 6.824 的优点

* 优点在于几乎没有上手难度 . 除了上述的前置条件外 , 不需要对这门课有任何的心理负担 . 在做lab时 , 所有需要知道的知识 , 这门课的课程设置都涵盖了 . 它甚至有一节专门讲述RPC和Golang , 还有一节TA课告诉学生实验里需要注意什么 . 
* 优质的实验设置 . 实验难度适中 , 最有意义的在于要实现一个真实可运行的Raft协议 . 
* 涵盖话题多 . 理论部分包括 , RPC、分布式系统的动机、复制状态机、各种一致性模型、分布式事务、分布式锁、Raft 共识协议、ZAB 共识协议、PoW 共识协议等等 . 应用部分介绍了多个对业界产生影响的产品 , 包括 , MapReduce、GFS、VMWare sphere、Zookeeper、Aurora、Frangipani、Spanner、Spark等等 . 

##### 课程实验的设置

* 实现一个简单的 MapReduce 框架 . 需要你知道 Unix Domain socket , 知道goalng plugin\(也就是动态链接\) . 
* 实现一个完整的Raft协议 . 这部分被拆成了三个部分 , 分别让你实现 Leader Election、AppendEntry RPC 和 Raft persist . 这一部分里 , 我们将使用实验提供的类库 labrpc 来完成完整的Raft协议 . 而 labrpc 是一个模拟网络环境的 rpc 框架 , 基于 UDP\(注意这一点\) . 
* 根据自己实现的Raft , 写一个KV数据库 . 同时实现 Raft 协议的 Snapshot RPC . 
* 为自己的KV数据库实现Sharding的功能 . 同时实现 multi Raft . 

#### 6.824 的缺点

* 6.824 的课程设置缺乏体系 . 6.824 整体的节奏就是 , 讲些 lab 可能需要的知识 , 讲点理论 , 讲讲论文 . 而整体缺乏一个清晰可见的脉络 , 导致它不成体系 . 
* 对一些比较艰深的事情没有涉及 . 比如 Lamport 尝试推动的想要通过 TLA+ spec 来对分布式系统进行 Safty & Liveness 的验证 . 可能这个部分太过理论 . 

### References

> 课程主要以2020为主 , 新的课程2021年2月16日开课 , 课程内容与2020年基本一致 , 多了一节Guest lecture , 由Golang的主要贡献者之一Russ Cox讲Go 语言 .

课程主页 - [https://pdos.csail.mit.edu/6.824/schedule.html](https://pdos.csail.mit.edu/6.824/schedule.html)

机翻全部课程 - [https://www.bilibili.com/video/BV1R7411t71W](https://www.bilibili.com/video/BV1R7411t71W)

* 字幕组Github - [https://github.com/ivanallen/thor](https://github.com/ivanallen/thor)

翻译课程 - [https://www.bilibili.com/video/av91748150](https://www.bilibili.com/video/av91748150)

课程中文翻译 - [https://zhuanlan.zhihu.com/c\_1273718607160393728](https://zhuanlan.zhihu.com/c_1273718607160393728)

* Gitbook版 - [https://mit-public-courses-cn-translatio.gitbook.io/mit6-824/](https://mit-public-courses-cn-translatio.gitbook.io/mit6-824/)

学生指南 - [https://thesquareplanet.com/blog/students-guide-to-raft/](https://thesquareplanet.com/blog/students-guide-to-raft/)

* 掘金翻译版 - [https://juejin.cn/post/6865538652961767431](https://juejin.cn/post/6865538652961767431)

相关开源书DDIA - [https://github.com/Vonng/ddia](https://github.com/Vonng/ddia)

#### 其他文献

> Google老三篇 , Lamport论文

**MapReduce** : Simplified Data Processing on Large Clusters 04OSDI

Jeffrey Dean and Sanjay Ghemawat

https://pdos.csail.mit.edu/6.824/papers/mapreduce.pdf

[https://blog.csdn.net/active1001/article/details/1675920](https://blog.csdn.net/active1001/article/details/1675920)

**GFS**

For atomic rename is important for Mapreduce

The Google File System

Sanjay Ghemawat, Howard Gobioff, and Shun-Tak Leung Google 03SOSP

[http://mpaxos.com/teaching/ds/20fa/readings/gfs.pdf](http://mpaxos.com/teaching/ds/20fa/readings/gfs.pdf)

[https://segmentfault.com/a/1190000023309479](https://segmentfault.com/a/1190000023309479)

**Big Table**

[http://arthurchiao.art/blog/google-bigtable-zh/](http://arthurchiao.art/blog/google-bigtable-zh/)

#### Lamport论文

**logical clock**

[http://lamport.azurewebsites.net/pubs/time-clocks.pdf](http://lamport.azurewebsites.net/pubs/time-clocks.pdf)

**paxos & multi paxos**

[http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf](http://research.microsoft.com/en-us/um/people/lamport/pubs/paxos-simple.pdf)

[https://juejin.cn/post/6844903683788898312](https://juejin.cn/post/6844903683788898312)

**raft**

[https://ramcloud.atlassian.net/wiki/download/attachments/6586375/raft.pdf](https://ramcloud.atlassian.net/wiki/download/attachments/6586375/raft.pdf)

[https://github.com/maemual/raft-zh\_cn](https://github.com/maemual/raft-zh_cn)

