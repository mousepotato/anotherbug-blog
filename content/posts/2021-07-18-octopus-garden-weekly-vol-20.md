---
title: "章鱼花园 Vol. 20: Dream big, the sky is NOT the limit" # remove yyyy-MM-dd prefix in the filename 
date: 2021-07-18T10:27:06-07:00
draft: false
hidedate: true 
tags: ["章鱼花园期刊"]
categories: ["Technique"]
featured_image:
description:
---

#### 科技
- [The dawn of a new space age](https://www.space.com/virgin-galactic-richard-branson-unity-22-launch-reaction)  #Quotes  #Thought-provoking 
	- I was once a child with a dream looking up to the stars. Now I'm an adult in a spaceship looking down to our beautiful Earth. To the next generation of dreamers: if we can do this, just imagine what you can do. - [Twitter By Richard Branson ](https://twitter.com/richardbranson/status/1414289206717865984)
- [OpenTracing 详解](https://pjw.io/articles/2018/05/08/opentracing-explanations/) 比较老的一篇文章，介绍了 OpenTracing 的基本背景，适合考古。OpenTracing 现在已经和 [OpenCensus](https://opencensus.io/) 合并成 [OpenTelemetry](https://opencensus.io/). #DevOps 
	- 分布式跟踪 （Distributed Tracing）鼻祖是基于 Google 的 Dapper 系统和论文。开源实现包括 Twitter 的 [Zipkin](https://github.com/openzipkin/zipkin) (基于 Scala)，Uber 的 [Jaeger](https://github.com/jaegertracing/jaeger) （已经加入 CNCF），SourceGraph 的 [appdash](https://github.com/sourcegraph/appdash)
	- Dapper 的设计理念在于如何精准的定位调用链路，如何从各个分布式系统里面收集数据就是不包含在内。 OpenCensus 为此提供解决方案。
	- 关于 OpenTracing 的集成方式：侵入方式，作者建议采用 Jaeger，在 Trace 的起始处，将 Trace ID 设置为 Request ID。非入侵式可以通过 Service Mesh 方式，比如 [Istio](Istio) Service Mesh 是在网络层面做文章，通过 Sidecar 的方式为 Pod 增加一层代理，通过这层网络代理来实现一些服务治理的功能，因为是工作在网络层面，可以做到跨语言、非入侵。
	- [Hot R.O.D. - Rides on Demand](https://github.com/jaegertracing/jaeger/tree/master/examples/hotrod)  OpenTracing 的官方 Demo.
- [thesephist](https://thesephist.com/) a writer and software engineer working on and thinking about opportunities in education, technology, and community. #Reading #Life 
- [100 Rabbits](https://100r.co/site/about_us.html) [Rek](https://kokorobot.ca/) is a writer and illustrator, [Devine](https://xxiivv.com/) is a programmer and musician, together we operate the **Hundred Rabbits** research lab, aboard [pino](https://100r.co/site/pino.html), where we do experiments on resilience and self-reliance through low-tech solutions. #Life 
- SoC vs DoD: **State of charge (SoC 充电程度)** is the level of charge of an electric battery relative to its capacity. The units of SoC are percentage points (0% = empty; 100% = full). An alternative form of the same measure is the **Depth of Discharge (DoD 放电深度) **, the inverse of SoC (100% = empty; 0% = full). SoC is normally used when discussing the current state of a battery in use, while DoD is most often seen when discussing the lifetime of the battery after repeated use. #Technology 
- [Open-source alternatives](https://opensource.builders/) Find open-source alternatives for your favorite apps #Tools 

#### 人文
- [德语：Röstigraben (土豆饼鸿沟)](https://en.wikipedia.org/wiki/R%C3%B6stigraben)土豆饼鸿沟一词最早出现在第一次世界大战期间，源于瑞士德语区的特色食品瑞士土豆饼（德语：Rösti）。在一战中，由于法德两国交战，中立国瑞士的人民因语言而发生分歧，法语区同情法国，而德语区支持德国。Rösti 是一道传统的德瑞风味菜肴，主要由煎土豆制成，马铃薯作为主要食材，有时还会配以培根、洋葱和奶酪。虽然这条顺着萨林河（Sarine）走向的“鸿沟”并不在地图上，但这条思想的边界还是被居于瑞士的人们从小铭记在心。正如这篇 [存在于瑞士的无形语言边界](https://keep.moe/2018/04/01/switzerlands-invisible-linguistic-borders/)翻译文章所说的「每当谈到“边界”时，我们最常想到的是政治分界线——那个将两个国家分开的冰冷界线，或是一堵墙。除了这种边界，还有更多——文化边界、语言边界、思想的边界。」 #Culture
- [IT 工程师养生指南](https://riboseyim.gitbook.io/perf/health) #Life 
- [《永隔一江水》—被传唱的经典背后是一个悲凉的爱情故事！](https://www.sohu.com/a/200483644_650497) 
-  「知我者谓我心忧，不知我者谓我何求」──《诗经・王风 ・黍离》 #Quotes 
- [Hotel Turndown service](https://en.wikipedia.org/wiki/Turndown_service) 酒店开夜床服务：在酒店业，夜床服务（开夜床）是指酒店员工将宾客的床上用品翻开，以备宾客睡眠使用的行为。 在开过夜床的枕头上，一般会放置一些甜点，例如巧克力或薄荷糖。 一些酒店还会提供更精致的夜床服务，例如为孩子提供睡前故事，为年轻夫妇提供鸡尾酒等。 #Life 

#### 随想


### 订阅章鱼花园

- Substack: [https://octg.substack.com](https://octg.substack.com/)