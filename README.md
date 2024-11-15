# Shanghai SAP VT 面经

申请岗位：Software-Design and Development 开发岗

申请周期：于2024/10/19日投递了简历，2024/10/28日晚7点参与笔试，预约了2024/11/1日的面试（15分钟），并于2024/11/15日参与线下面试。HR说将于2024/11/18日通过邮件的方式发送PreOffer。整个流程的事件周期差不多为一个月。

## 一. 投递简历

需要投递一份简历Personal Resume，一份求职信Cover Letter和一些辅佐材料。

## 二. 笔试

考试总时长两个小时，分为20道选择题（共60分），和2道编程题（共40分）。

选择题涵盖的范围非常广泛。Java，数据库，云，计算机网络，甚至包括对SAP产品的了解，都有涉及。

第一道编程题：用“-”和“o”表示糖葫芦串，比如“-oo-ooo”。一连串“o”与单边的“-”构成一个合法糖葫芦串，比如“-ooo”或“oooo-”。找最长合法糖葫芦串中“o”的数量。

这道题比较简单，只要在同时存在“-”和“o”的糖葫芦串中，统计**最长连续**“o”的个数即可。

第二道编程题：有一个第一行为1，第二行为2，第N行为N个格子的区域。每一个格子都有一些金币，只要站在格子里就能拿到里面的金币。你站在最左上角的格子里，每次可以从一个格子走到它右边或下边的格子里。请问如何走才能拿到最多的金币。
输入格式：第一行输入一个正整数n。以下n行描述该方格。金币数保证是不超过1000的正整数。

先从简单的问题入手，如果是N*N的区域呢？

使用动态规划解决问题，把走到每个格子能获取到的最大金币数量列出来。因为只能朝下或右走，意味着若走到当前格子，一定经过上边的格子或左边的格子，只要将上边或左边格子中已经计算出的最大金币数（更大者）加上当前格子中的金币数就可以算出“走到当前格子可以获得的最大金币数”。所以分为两个步骤：

① 考察特殊区域，最左边一列和最上边一行的没有更左边或更上边的区域，所以只能拿各自左边或上边来计算。

② 遍历计算除了特殊区域每个格子。

③ 输出右下角格子的最大金币数。

那么对于题目的要求的三角形区域也比较容易了，特殊区域就是最左边一列和三角形的斜边。对于斜边上的方格，上方没有格子，只能用左边的格子进行计算。在N*N的区域的情况下，第②步中，判断当前是否在斜边上，若是，则只用左边格子中的最大金币数计算。

感觉笔试不会筛人，选择题基本没有确定的，随便乱选。编程题第一题能写出来就行。

## 三. 电话面试

电话面试需要和对应的HR预约时间，总时长15分钟，实际上我匹配到的HR非常和蔼，10分钟就结束了（夹杂着玩笑和对本人学校三学期制的吐槽）。这一面本质应该是简历面和小型英语测试。我面试前十分钟从网上了解到需要英语自我介绍，赶忙准备了一下，结果没用到，连自我介绍都不用。HR是按简历的顺序提问。

① 教育经历。因为我在华东师范大学辅修汉语言，简单问了我一下为什么要选择辅修。
② 项目经历。问我在某项目中担任什么角色，做了哪些事情。
③ 实践经历。志愿者经历。问我ICPC是什么，做了哪些工作。
④ 英语考核。HR自己英语也不是特别标准，照着稿子读，加上电话信号不好，我只听到了前半个问题。“呃”了一会儿，HR也理解我，直接说“没事，就回答前半个问题就行。”前半个问题是，下周有什么规划。
⑤ 反向提问。

或许是我匹配到的HR人比较好，整体面试的氛围很轻松，像仅仅是核对了一下简历上写的细节一样。

## 四. 群面

早上9点左右到公司，9点半开始面试，到11点准时结束。共6位面试官，2位技术面试官，4位HR（有一个是进行电话面试的）。一组7个人面试，我所在的组共有4个同济大学的，1个华东师范大学的和2个上海大学的。

### 1. 无领导小组讨论

背景：零售商公司希望引入人工智能技术，但是有所顾虑。请选择一个领域，提出方案。

参考：价格优化；销量和库存优化；商品的陈列；用户意见等。

任务：① 要求提供技术架构和实现。② 可能存在的隐患：风险评估；员工对新技术的接受程度；技术出现故障的影响。③ 估算成本：硬件；软件；人力成本。

要求：3分钟阅读（之后关闭），20分钟讨论，2分钟选一个人总结陈述，2分钟补充。

由于我第一次参与无领导小组讨论，没什么经验。觉得3分钟信息的记录和对整体流程的控制有文章可以做。本组基本上是有意见就发表，自然而然地推进流程。

本组最终提供的陈述大致内容如下：选择了<u>价格优化领域</u>，因为其是核心、可量化。目标是通过人工智能技术动态调整价格以获得销量和库存的平衡。分为两个层次，第一个层次是<u>前期调查、用户调研，采用NLP技术提取重要的信息</u>。<u>第二个层次是在前者基础上分析自身、竞争对手和潜在竞争对手财务报告的分析，采集数据集进行神经网络的训练</u>。通过控制对价格的更新频率以提升员工对新技术的接受程度。对于技术预估不准确，可以以版本的形式更新，保留回退可能性，<u>在不同地区采取不同的方案进行试点</u>。<u>软件上需要云存储和计算的支持。人力成本主要涉及数据收集团队、技术团队和培训团队。</u>（下划线表示本人参与提出意见的部分。说实话，实在没提出什么具体的技术，只是说用神经网络去做啦、用NLP做啦、CV应该用不上吧...这类飘得很的话。）

### 2. 技术面试

两个面试官轮流问问题。A主要问一些设定的问题，B主要问一些开放性问题（主要是前端）。

前面两个问题（好像是和Java有关的，大家好像都是搞Python的）没有一个人回答，所以记不清了。下述*表示基于上个问题的进一步提问。

【语言】

A：简述一下Python中字典、元组、列表、集合。

A*：为什么Pytorch中要使用元组传参？

【数据库】

A：如何创建一个数据库。

A*：如何设计一张表（范式）。

A*：Postman相关。

【GenAI】

A：有没有尝试过调OpenAI或者其他GenAI的API？

A*：使用API时需要调整的参数（4）。

【GitHub】

A：有没有使用GitHub的经历？

A*：Git中fetch和pull的区别？

A*：pull request的流程？

【前端和云】

B：对“云服务”的理解，对其未来发展的看法。

A*：SAP op和SAP Cloud。

B：Web3.0和Web1.0的区别。

其他

A：有无软件测试的经历？

A*：如何进行单元测试？

最后还有一道【软件架构设计题】，是一个园区停车场管理系统。要求区分用户，有员工身份检验，前后端分离，集成物业收费系统等。10-15分钟画出来。

提的问题还有很多，毕竟差不多有两个小时都在技术面试，会就举手回答，可以补充，不会沉默就行。大家都不会的时候氛围也挺好，会直接换下一个问题。面试官后来说，因为大家都是大三学生，不是工作了一两年的学生，肯定不会刁难大家。

总的来说，因为各位面试官人都很和善，面试的时候也不是很紧张，如果对问题有印象就回答了。结束后留了大家吃饭，伙食还可以。
