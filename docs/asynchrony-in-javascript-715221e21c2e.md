# JavaScript 中的异步

> 原文：<https://javascript.plainenglish.io/asynchrony-in-javascript-715221e21c2e?source=collection_archive---------11----------------------->

![](img/823586682676456049d5c84c6fea9777.png)

Photo by [Sudharshan TK](https://unsplash.com/@shantk18?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

因为 JavaScript 是众所周知的单线程语言，所以异步是良好代码性能的关键。

在最开始，只有“回调”，然后我们得到承诺，现在我们也有异步/等待。尽管很少使用“回调”来创建新代码，但是仍然有一些代码在使用它们。对于大多数正常情况，我们将使用 Promise 或 async/await。让我们看看每种情况下不同的例子，以及在它们之间进行选择的一些技巧。

# 复试

即使在新的 API 版本中，一些模块已经被更新为使用基于承诺的行为，重要的模块仍然在使用回调。一个重要的例子可能是“流”。

流仍然依赖于回调，让我们看一个例子。

正如我们所看到的，知道写入过程何时结束的唯一方法是在结束时有一个回调来接收调用。

当然，如果您愿意，您可以更改这一点，并使用 Promise 来封装回调过程。让我们看看怎么做。

# 承诺

承诺已经成为异步任务的“必经之路”。新的 [ECMAScript](https://es.wikipedia.org/wiki/ECMAScript) 版本改进了原生 Promise API，我们总是有像[蓝鸟](http://bluebirdjs.com/docs/getting-started.html)这样的模块，它们给我们提供类似于。点击“，”。道具“，”。map”或 catch(类似于我们在 Java 等语言中所做的)。

Promise 帮助我们创建了一个很好的函数式代码，让我们将代码看作是一个由不同步骤组成的过程。让我们看一个例子。

正如我们所见，遵循流程并理解整个流程非常容易。在这种情况下，流程使用一种方法在函数之间传递对象，并且每一步都为下一步完成数据。但有时这是不可能的，或者我们可能不想创建一个大对象并将其传递给每个方法，因为该方法可能是外部的，需要一个具体的输入并有一个定义的输出，或者该过程需要保存数据以供以后使用。我们来举个例子。

# 异步/等待

这种创建异步代码的方式有助于我们获得更具命令性的代码，有时比一连串的承诺更容易阅读。当我们需要获取不同的数据并保存以备后用或避免创建复杂的结构时，它也能帮助我们。让我们看一个使用 async/await 的例子。

有时，当我们切换到使用 async/await 而不是 Promise 时，我们可以选择一个性能较差的实现。在最后一个例子中，“getFriends”和“get 敌国”并不相互依赖，它们可以被同时调用，但是我们的实现让我们等待一个完成后再启动另一个。让我们看看如何改善这一点。

正如我们在上一个例子中看到的，两者的结合可以使我们的代码易于阅读并且仍然具有高性能。

总之，在 Node.js 中创建异步代码有不同的方法。为每种情况选择最佳的方法取决于我们。对我来说，这些是我在创建代码时要遵循的一些规则(从重要到不重要):

*   易于阅读。守则是给同事看的，所以要简单易懂。
*   易于扩展-更改。
*   在不破坏之前的基础上，尽可能地提高性能。

*更多内容看* [*说白了. io*](http://plainenglish.io/) *。在这里注册我们的* [*免费周报*](http://newsletter.plainenglish.io/) *。*