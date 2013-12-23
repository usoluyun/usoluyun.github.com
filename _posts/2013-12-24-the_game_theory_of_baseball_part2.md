---
layout: post
title: 棒球的博弈论 part 2 
---

#棒球的博弈论 part 2 

> **前言** 
> 本章我们来结合博弈论的理论，来探讨投打双方选择不同策略对于比赛结果的影响。
> 既然数据显示Zito在对阵Anderson时候并不好，那到底不好在哪里呢？仅仅是上垒率低么？如何来量化巨人队这个选择到底对比赛的胜负影响有多少呢？

###Zito vs Anderson  

尽管我们从博弈树里得出了结论，但是巨人队的教练依旧选择了让Zito留在场上对付Anderson。虽然有左头克制左打者的优势，Anderson职业生涯对阵Zito仍然有.384的上垒率（高于职业生涯平均.325).为了理解和分析这轮打席的博弈决策，我们来看一下投手和打者第一级的决策：投好球还是投坏球，挥棒还是不挥棒。

![Zito vs Anderson](http://media-cache-cd0.pinimg.com/originals/a2/0c/b8/a20cb807b408600ad032551463863a20.jpg)

为了确定，每个球员的最佳选择，我们必须制定每一球的收益。在这个游戏中，收益必须是对称的，也就是对打者来说好的结果，就是对投手来说差的结果。（必须是零和博弈，也就是非胜即败），并且忽略一些第三方因素比如球员的名气大小，收入高低。  

我们用WPA来定义四个可能的结果的收益。对于Anderson来说，在道奇球场（主场）一出局，垒上无人，八局下半一球落后，可能的收益如下：

![Anderson's Payoffs](http://media-cache-ec0.pinimg.com/originals/5b/a6/39/5ba639958b93bcce0a2993f11e627f2b.jpg)  

运用这张表格，我们就可以来衡量每个反应影响道奇获胜的程度了。比如当Anderson选择挥棒，那么就不会出现坏球（ball）的局面，可能的局面就是一垒安打，二垒安打，三垒安打，本垒打，出局，或者挥空。根据anderson职业生涯的统计，我们可以算出他得出以上情况的概率。因此

Payoff of an Anderson Swing in the Zone:    

> (Contact rate x WPA/hit) + (out/contact x WPA/out) + (1-contact rate) x WPA/strike    

Where WPA/hit is:    

> WPA x (1B/contact) + WPA x (2B/contact) + WPA x (3B/Contact) + WPA x (HR/Contact)    

运用这两个公式，我们能得出之前四种结果的概率。因为棒球是个零和博弈，所以道奇获胜的概率等于巨人失败的概率，因此，之前那个矩阵的结果就是：  

![Result of Zito Vs Anderson](http://media-cache-cd0.pinimg.com/originals/bc/d8/10/bcd8109c6d6bb7d6a40ce1db918409e6.jpg)  



在这里纳什均衡就是使用混合策略。 
> **什么是纳什均衡**  
> [维基百科条目](http://zh.wikipedia.org/wiki/納什均衡點)
> 纳什平衡，又称为非合作赛局平衡，是博弈论的一个重要概念，以约翰·纳什命名。  
> 如果某情况下无一参与者可以通过独自行动而增加收益，则此策略组合被称为纳什均衡点 
> **什么是混合策略纳什均衡**   
> [维基百科](http://zh.wikipedia.org/wiki/策略_(博弈論))  
> 相对于纯策略纳什均衡，混合策略纳什均衡同样是一个赛剧中的均衡点，不过它在每个给定信息下只以某种概率选择不同策略。

当前这个概率可以通过Zito的好坏球率和Anderson的挥棒几率来计算得出：

> Zito好球率是46.3%  
> Anderson的挥棒概率是87.9%  

那么对于Anderson来说他挥棒的话

> .55 x 46.3 + .08 x 53.7 = .298  
>  怎无论Zito投的是好球还是坏球，Anderson的收益是（.298%, -.298%)  

不挥棒的话  

> -1.50 x 46.3 + 1.85 * 53.7 = .3  

再来看Zito ， 如果他投进好求带的话 

> -.55 x 87.9 + 1.50 x 12.1 =  -.3  

如果他不投进好球带的话  

> -.08 x 87.9 + -1.85 x 12.1 =  - .3  

结果就已经很明显了，那就是  

***此刻Zito 对阵Anderson，双方尽自己最大努力（好球率46%，和87.9%的挥棒率），双方的收益差是 .3% vs -.3%  。Anderson将会占有先手。尽管这.3%非常小。这进一步证明了，巨人教练组不把Zito换下来是错误的。***   

###结果  

不幸的是，Zito没有达到自己46.3%的好球率，6个投球，5个坏球，Anderson放了其中的四个没有挥棒，被保送上了一垒。  

![Zito pitches against Anderson](http://media-cache-ak0.pinimg.com/originals/47/e3/86/47e38650bd0335f263c10db5a4f72a75.jpg)

***再根据之前不同局面的收益定义，道奇的WPA提高了7.4%。***



（未完待续）
