# 如何用 JavaScript 构建队列

> 原文：<https://javascript.plainenglish.io/how-to-build-a-queue-in-javascript-c2652500e82d?source=collection_archive---------20----------------------->

![](img/2f2922df9ddf816df2cafe19058faca4.png)

Photo by [Levi Jones](https://unsplash.com/@levidjones?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

你有没有在排队等什么东西的时候对自己说:“我想知道这是一种什么样的数据结构？”

没有吗？我也没有。但是数据结构是我们生活中提供秩序的基础，它们无处不在。它们也是计算机科学和算法设计的基础，这使得对数据结构的深刻理解对获得软件工程工作至关重要。

# 行列

队列是软件工程和其他学科中使用的一种有用的数据结构，它有一些特殊的属性，使得它在这些领域中特别重要。队列遵循先进先出(FIFO)规则，在队列中时间最长的项目将是下一个被移除的项目。

![](img/df6c98c351b6d5e9409249e592c47906.png)

Photo by [Mihály Köles](https://unsplash.com/@mihaly_koles?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

就像人们在滑雪缆车上、乘自动扶梯上或在几乎任何种类的队伍中一样，队列在现实世界中随处可见。你的顺序取决于你相对于其他人在队列中的位置。如果你前面没有人，那么你就在队列的最前面。

在这种设置中使用这种数据结构的好处是不需要任何额外的机制；维护秩序不需要任何额外的开销。因此，这种数据结构的一个缺点是，您必须一直留在队列中。这种数据结构的其他变体缓解了这个问题，比如肉店的售票系统或在 DMV 等待你的号码。这些变体仍然使用排队系统，但是您不需要实际排队，因为您被分配了一个号码，并且该号码代替您留在队列中。

# 效率

使用数据结构时，效率至关重要。使用错误的数据结构会导致应用程序效率低下和用户体验不佳。因此，为您的算法选择正确的数据结构非常重要，而效率是我们用来做出这些决定的衡量标准。我们通常使用[大 O 符号](https://en.wikipedia.org/wiki/Big_O_notation)来描述时间和空间复杂性，你可以在这个[备忘单](https://www.bigocheatsheet.com/)中看到流行数据结构的比较。

在比较数据结构时，我们通常主要对它们的时间复杂度感兴趣，因为孤立的数据结构的空间复杂度几乎总是线性的(即`O(n)`)。在评估时间复杂度时，我们通常也对最坏的情况感兴趣。这是因为，对于少量的数据，时间复杂度通常是微不足道的和不可靠的。

如果使用得当，队列非常适合插入和删除。这是因为只有一个位置可以插入项目(在队列的后面)，也只有一个位置可以删除项目(在队列的前面)。由于这些限制，队列具有插入`O(1)`的时间复杂度，或者“恒定”时间复杂度。但是，如果您需要能够查找除了队列前面的项目之外的任何其他项目，那么您就不走运了。您需要让每个项目出列，直到到达目标项目，这通常是不可行的。在这种情况下，您的时间复杂度将是`O(n)`，您可能想要考虑不同的数据结构来满足您的需求。

# 用 JavaScript 实现

最起码，一个队列需要能够将一个项目入队，将保留时间最长的项目出队，并允许用户读取它的长度。下面是 JavaScript 中一个基本队列的功能实现。

首先，您可能注意到我选择使用一个`function`而不是一个`class`来实现这个队列。这是因为我想保持收件箱和发件箱的私密性，我使用了 JavaScript 闭包来实现这一点。如果我使用一个`class`来实现这个，我会把收件箱和发件箱放在`class`实例上，这将把它们暴露给外部范围。

其次，你可能已经注意到我正在调用一个`Stack`函数。这是 JavaScript 中的一个栈的自定义实现，如果你想了解我是如何构建它的，请阅读我以前的文章[如何在 JavaScript 中构建一个栈](https://medium.com/nerd-for-tech/how-to-build-a-stack-in-javascript-49d2125082a8)，在那里我详细介绍了栈实现背后的所有细节。堆栈使用后进先出(LIFO)原则，并经过优化，为插入和删除提供恒定的时间复杂度(即`O(1)`)。

堆栈在这里发挥作用是因为效率。一个简单的队列实现可能只涉及一个数组，在这个数组中，通过将项插入到数组中的索引 0 处，并将其余的项移动 1 个索引来对项进行排队。数组中的“移位”代价很高，并且会使插入时间复杂度呈线性，或称为`O(n)`。

为了避开这个限制，我们可以实现两个堆栈:一个收件箱和一个发件箱。当项目进入队列时，我们将它们推入收件箱堆栈。该操作具有恒定的时间复杂度。每当我们需要将一个项目出队时，我们首先检查发件箱中是否有任何项目。如果至少有一个项目，我们就简单地把它从堆栈中取出并返回那个项目，这是恒定的时间复杂度。如果我们的发件箱是空的，但我们的收件箱有项目，我们弹出收件箱中的每一个项目，并将其推到发件箱堆栈上。该操作被认为是“分摊”的恒定时间复杂度。我们使用术语“摊销”来描述偶尔比它们的典型时间复杂度更差的操作。在我们的例子中，我们有固定的出列时间，直到我们用完了发件箱中的项目。然后我们有一个`O(n)`操作将所有的项目从收件箱移动到发件箱。因为这只是周期性地发生，而不是在每个出列请求上，我们可以说这个操作是常数摊销时间，或`O(1)+`。为了清楚起见，我在下面举例说明了这些操作。

![](img/e3d5803cfc4a357c8d9e2cc54e744a08.png)

An illustration of using two stacks to implement a queue

一旦理解了心智模型，代码就相当简单了。我们返回一个对象，它有一个入队方法、一个出队方法和一个大小获取器。Enqueue 将目标项目推入收件箱。出列检查发件箱中是否有项目，如果有，它将弹出最新的项目并返回。如果我们不这样做，它将运行我上面举例说明的逻辑，然后弹出最新的项目(如果有的话)。最后，size getter 只是返回堆栈大小的总和。

# 结论

队列在我们的生活中非常常见，是软件工程中使用的基本数据结构。如果使用得当，它们可以高效地插入和删除数据。希望这篇文章有助于澄清队列，但是请在评论中告诉我任何一种方法！

*最初发表于*[T5【https://codingbootcampguides.com】](https://codingbootcampguides.com/how-to-build-a-queue-in-javascript)*。*

*更多内容请看*[***plain English . io***](http://plainenglish.io)