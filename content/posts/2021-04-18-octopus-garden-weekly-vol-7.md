---
title: "章鱼花园 Vol. 7: If you can't beat them, join them." # remove yyyy-MM-dd prefix in the filename 
date: 2021-04-18T10:18:58-07:00
draft: false
hidedate: true 
tags: ["章鱼花园期刊"]
categories: ["Technique"]
featured_image:
description:
---

#### 科技
- 一个历史：在2013年5月，Node.js 包管理器 npm 的作者 Isaac Z. Schlueter，宣布 Node.js 已经废弃了CommonJS，原因是 CommonJS 只指定标准而与实现和实际需求脱离，这与 Node.js 的目标相背离。同时也反思了「"Standardizing" before you have implementation is naive, in the most literal sense of showing a lack of experience, wisdom, or judgement.」，同时也指出 Node.js 与其他 SSJS （Server-side JS) platform 之间的竞争与 MSIE and the browser war 的不同，值得一读。[Forget CommonJS. It's dead. We are server side JavaScript.](https://github.com/nodejs/node-v0.x-archive/issues/5132#issuecomment-15432598)

- 沙拉查词，[一款 Chrome 划词翻译插件](https://saladict.crimx.com/download.html)，[可以配合 ANKI 使用](https://saladict.crimx.com/anki.html)，这是作者的[博客](https://blog.crimx.com/about)。


- [当「无可奉告」无可奉告——反思与告别](https://www.bilibili.com/video/BV1Rp4y187ZJ) ：「无可奉告」是交大的匿名 APP 论坛，短暂的持续了一段时间，2020/12/04 - 2021/04/11，视频是创作者们最后的告别。愿为江水，与君重逢。一定要看到最后。


```
The Zen of WKFG 无可奉告之禅  
  
Love is better than hate. 爱胜于恨  
Real is better than fake 真实胜过虚假  
Beautiful is better than ugly. 美丽胜于丑陋  
Friendly is better than aggressive. 友善胜于好斗  
Sound is better than reticence. 发声胜于缄默  
Equality is better than disparity. 平等胜于差异  
Unease is better than comfort. 忧患胜于安乐  
Pursue is better than abide. 追求胜于遵守  
Respect is better than understand. 尊重胜于理解  
Understand is better than ignorance. 理解胜于无知  
Ignorance is better than prejudice. 无知胜于偏见  
Every voice counts. 每个声音都很重要  
Special cases aren't special enough to break the rules. 特例也不可违背这些规则  
Injustices should never pass silently. 不公正绝不能无声无息地过去  
Unless, no unless. 没有例外  
  
「无可奉告」2020/12/04 — 2021/04/11
```

- [从 DevOps 到 AIOps，一文聊聊面向终态的监控平台建设](http://www.greatops.net/?id=254 ) ：我总觉得终态也始终是局部终态。「初心」与「终态」可能是解决问题的两个思考切入点。如果重新来设计云计算服务，会有什么不同呢?  #Technology 
	-  [清华大学裴丹 Netman 实验室](https://netman.aiops.org/talks/)
	-  [智能运维系列](https://zhuanlan.zhihu.com/p/188634867)

> 最后，与大家共勉：智能运维落地， 前景是光明的，道路肯定是曲折的。引用一下我原来在AT&T的领导Albert Greenberg在2015年SIGCOMM演讲的时候说的两句名言。他说别人问我：你怎么得了那么多的学术界会议的Test of time奖（十年前发的论文，十年后再评哪篇论文是最好的）的？他说很简单，“论文发表之后再花五年把论文里面的算法变成产品，就证明你这个东西是好的，就自然得这个Test of time奖了”。
>  他的意思就是你要把好的思路、好的算法在应用中实践出来，并且对工作量有合理的预估。他的另外一句名言是“人们往往高估两年内能完成的成果，同时又往往低估五年内能完成的成果。” 意思是如果你看太短的话，很多事情做不成。但是有足够的耐心，放到四五年的尺度的话，往往能做成很多的事情。 - 清华裴丹

- [chia 币](https://www.chia.net/)  3月19号开始加入主网 Mainnet，全面开启了硬盘挖矿时代。在全球 GPU 显卡出现疯抢之后，下面就要开始是硬盘了吗？[中国以及香港市场的 4T-8T 硬盘已经全面涨价。](https://www.tomshardware.com/news/hard-drive-ssd-shortages-imminent-if-new-cryptocurrency-blooms) 
	- 原理：Chia 币是基于 Proof of space and time 来做共识，或者说你拥有的空间数量。它有两个形式，首先是 plotting 然后是 farming，形象一点就是先耕种 (plot) 然后收获 (farm)。Plot 的过程是会持续的做大量 CPU 运算（sort） 和硬盘读写，最终生成一个 plot 文件（ K32 是 ~101.4GB），第二个阶段是基于你手上的 plot 文件（戏称农民手里的「牌」）等待系统「翻牌」，然后拿到 XCH （chia币）
	- Plot 过程会对硬盘做持续读写，推荐是 datacenter SSD，普通的机械硬盘或者 SSD 可能很快就会挂掉。
	- XCH （chia币）的价格未知，挖矿的程度已经越来越难。[XCH/TiB 的关系](https://www.chiaexplorer.com/charts/xchTib)（每 1TB 空间每天获得的 XCH 数量）逐天递减。大概 10TB空间10天时间从可以获得 5 XCH (4/5/21) 到现在的 2.3 XCH (4/18/21) 个。
	- 微信上有人说：「我忽然想明白了，加密货币是不是不需要落地场景，只需要共识。因为货币就是共识的产物，币有多贵就是看有多少韭菜的共识。」嗯，而且，最最主要的「傻X的共识也是共识」，你到底要不要做呢？If you can't beat them, join them.

#### 人文
- 游戏运营的三个生命周期：1）能来玩（新进 come) 2）可以玩 （活跃 play）3）喜欢玩（活跃 stay）。是否也是用户上瘾的模型。 #Products 
- 「识时务者为俊杰」英文翻译：Ones who understand situations and act accordingly, are the elites.
- 「无力胜之则从之」英文翻译：if you can't beat them join them.

#### 随想
- [Boilerplate Advice](https://www.ribbonfarm.com/2021/01/06/boilerplate-advice/)  样板人生的建议。当中提到了   Emerging Adulthood 的几个阶段： 
	- 18 - 30 是第一次人生自我独立做主「Get worldly, develop relationships (including with yourself), learn who/what to trust, thread the needle of cynicism vs. motivation. Learn to be kind to yourself.」
	-  Act 1: 30 - 42岁 「Pick risks, battles, commitments, and responsibilities that will make you who you are.」 你的选择定义了你自己。 
	-  Act 2: 42 - 54 岁 「Understand your own past, and make your peace with it. Decide what/who to forgive/forget — or not.」
	-  作者毕竟年轻， 55-70 还是TDB，殊不知，几千年前孔子早就告诉我们了：「三十而立，四十而不惑，五十而知天命，六十而耳顺，七十而从心所欲，不逾矩」。

### 订阅章鱼花园

- Substack: [https://octg.substack.com](https://octg.substack.com/)