# 一个有趣的编程错误差点让我的主管丢了工作

> 原文：<https://javascript.plainenglish.io/a-funny-programming-mistake-that-almost-cost-my-supervisors-job-c360bb9cbdcf?source=collection_archive---------1----------------------->

## 我估计很多创业公司也是这样。

![](img/b4c0a1d181642ef60bbbd96dada02f11.png)

Photo by [Ketut Subiyanto](https://www.pexels.com/@ketut-subiyanto?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels) from [Pexels](https://www.pexels.com/photo/stressed-black-male-entrepreneur-working-on-laptop-in-park-4560092/?utm_content=attributionCopyText&utm_medium=referral&utm_source=pexels)

一个有趣的错误和一小时内 50 个额外的电话。你能想象吗？我几乎忘记了这个故事，但我通过手机上的一个应用程序再次记住了它。

我同事做的 app 也发生了同样的事情。所以让我们进入故事。

# 我们在一家初创公司工作

我们都在一家成立一年的初创公司工作。你知道在创业公司工作有多难，多有挑战性。这是一样的！

包括我在内，只有三个开发人员。首席工程师必须维护很多东西。他独自处理所有的后端任务。他必须编写所有的后端代码，在云端部署代码以及其他许多事情。

我为什么要说这些？因为他是最优秀的程序员之一，我见过谁能在巨大的压力下工作。所以在讲述这个有趣的事件之前，你需要知道这个。

# 我们没有测试人员

由于开发人员很少，我们不得不自己测试所有的代码。难的是在测试期间我们都累了。

我坚信测试人员对于一家科技初创公司来说非常重要。为什么？

*   开发者(任何人)都不容易发现自己的错误。(如果他们找到了，他们会在编写代码时解决这个问题)
*   有时他们被最后期限弄得筋疲力尽，他们的大脑想要忽略这些错误。

正如我前面所说，我们的首席开发人员必须自己编写所有的后端代码。所以有一天，他犯了一个有趣但严重的错误。

# 我们使用 firebase 发送通知

我们使用 firebase 云消息来发送通知。我们有一组测试用户，我们的首席工程师在那里发送测试通知。

我们在做会计软件，客户可以用钱给虚拟点数充值。我们有 500 多名顾客。

我们的首席工程师犯了一个错误，从 firebase 控制台向所有客户发送了一个真实的通知！！通知并不简单！通知是:

> 您的帐户已被扣除 X(我不记得金额)点。

一些客户不明白这是一个错误。因此，50 多名客户在一个小时内致电我们的客户服务号码，询问他们的账户为何被收费！

当我们解释这一事件时，一些人认为这是一个有趣的错误，但大多数人都很愤怒！他们没有检查自己的余额，更确切地说，没有检查交易历史。

我们特工在说明情况的时候，反复问为什么要收费？甚至他们解释说是假消息，却问为什么发假消息！这是一个很好的问题，大多数客户对这只是一个错误的回答并不满意！

老实说！这不是什么值得高兴的事情。这是一个关于公司及其产品的危险信号。

然而，为了留住客户，我们的 CEO 给了所有的顾客优惠券。尽管如此，那天晚上我们还是失去了至少 15 个客户。

# 我们的首席执行官非常生气

我们的首席执行官非常愤怒，他想在那天晚上解雇我们的首席工程师。但对他来说好的是他没有。因为如果他这么做了，整个团队就没用了。我们的主管做了一半以上的工作。

但他确实在七天内雇佣了一名测试人员。但是我们的首席工程师对此感到非常惭愧。他对这个错误并不感到内疚。这是创业公司必须面对的情况和羞辱。

没有人愿意犯错。当有人在巨大的压力下工作时，他们肯定会犯一些错误。

我不怪这里的任何人。由于财政状况，管理层不得不节省开支。虽然他们应该早点雇用测试员，但他们给了我们一份不错的薪水和其他福利。他们总是尊重我们。

我们不得不顶着压力工作，但他们从不强迫我们加班。但这对我们所有人来说都是一个很好的教训。

情况并不有趣，但这确实是一个有趣的错误，不是吗？

*更多内容看*[***plain English . io***](http://plainenglish.io/)