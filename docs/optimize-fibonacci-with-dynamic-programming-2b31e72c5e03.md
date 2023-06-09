# 用动态规划优化斐波那契

> 原文：<https://javascript.plainenglish.io/optimize-fibonacci-with-dynamic-programming-2b31e72c5e03?source=collection_archive---------5----------------------->

## 如何使用动态规划实现更好的时间复杂度的斐波纳契数列？

![](img/a90ad9809060b93d3c059978d5837a3c.png)

Photo by [Tyler Franta](https://unsplash.com/@tfrants?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

# 什么是斐波那契数列？

斐波纳契数列是一系列升序排列的数字。前两个数字之后的每个数字都是斐波纳契数，它必须等于前面两个数字的总和。例如，从 0 到 610 的斐波纳契数列:

```
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233, 377, 610
```

所以你可能会问为什么这个有用？嗯，斐波纳契数列在数学领域的应用比在编程领域更广。尽管它被认为是教授递归之类的有用工具。它也可以作为引入动态编程概念的一个问题，就像我们在这里要做的一样。

# 不用动态规划求解斐波那契

因此，为了开始弄清楚如何用动态编程解决斐波那契问题，我们应该首先知道如何用简单的递归来解决它。

所以这给了我们答案。但是为什么这不是最优解呢？我们知道，当使用递归时，每个函数调用都被推到调用堆栈上。对于这个具体的问题，我们可以把它想象成一棵有很多层次的递归树。

```
 fibonacci(6)
                           /            \
                          f(5)          f(4) 
                        /     \         /   \
                     f(4)     f(3)     f(3) f(2)
                     /  \     /   \       / \
                  f(3)  f(2) f(2) f(1)  f(2) f(1)
                 /  \
              f(2)  f(1)
```

正如您在这里看到的，递归函数调用产生了几个重叠的计算。这意味着我们的解决方案做了很多不必要的工作。这在求解 1 到 6 这样的小数字时可能没问题，但一旦我们扩大到更大的数字，这就成了一个问题。为了进一步理解我的意思，让我们添加一个 incrementer 变量来获得执行的计算次数。

例如，如果我们传入 7 个，我们将得到 13 个计算。但是让我们试试更大的数字，比如 20。

```
fibonacci(20); // 6765
console.log(numCalculations); // 21891
```

哇哦。这给了我们一个庞大的 21891 计算。您可能会想，这对这个解决方案的大 O 运行时没有好处。你是对的！有了这个解，我们得到的时间复杂度为 *O(2^n).*不是很快！

# 实现动态规划求解 Fibonacci

那么什么是动态编程呢？动态编程基本上只是一种优化技术。它通常用在有[重叠子问题](https://en.wikipedia.org/wiki/Overlapping_subproblems)的问题上，就像我们的斐波纳契问题，目前正在一次又一次地解决相同的子问题。

为了优化我们的斐波那契解，我们将使用一种叫做[记忆化](https://en.wikipedia.org/wiki/Memoization)的动态编程技术。这项技术的工作原理是将函数调用的结果存储在一个数据结构中，比如一个 hash map，然后在每次递归调用时检查它，看看我们是否已经针对那个特定的问题进行了计算。让我们用 Fibonacci 问题来实现这种技术，以优化我们的解决方案。

现在你可以看到我们添加了一些额外的代码，但是这个解决方案极大地优化了之前的方案，将运行时间降低到了 *O(n)* 。所以让我们回顾一下我们在这里做的事情。首先，我们将一个散列映射分配给一个名为`cache`的变量。这是一个很好的名字，因为我们所做的基本上是缓存函数调用的结果。然后在第 4 行，我们通过返回一个函数来利用 Javascript 中的[闭包](https://en.wikipedia.org/wiki/Closure_(computer_programming))的概念，这样我们就不会在每次递归调用时重置缓存变量。我们将`n`传递到我们的嵌套函数中，在第 6 行我们检查是否已经求解了`n`。我们还在第 8 行包含了我们的基本案例。第 12 行和第 13 行是我们执行计算、存储结果并返回结果的地方。

要运行这个函数，我们可以将函数定义存储在一个变量中，并使用作为参数传入的任何数字来调用它。

```
const callFib = dynamicFibonacci();
callFib(10); // 55
```

这给了我们斐波纳契问题的答案。让我们通过再次使用`numCalculations`变量跟踪计算次数来进一步证明为什么这个解决方案优于我们之前的解决方案。

让我们继续传递与上一个解决方案相同的数字，这样我们就可以比较两者。

```
const callFib = dynamicFibonacci();
callFib(20); // 6765
console.log(numCalculations); // 39
```

哇，我们这里只有 39 个计算。与普通的递归解决方案的 21891 次计算相比，这要少得多。

# 识别像斐波那契这样的动态规划问题

为了识别动态编程有所帮助的问题，我们应该问自己几个问题，例如:

*   这个问题可以分成几个子问题吗？
*   涉及递归吗？
*   子问题是否重叠？

这可能是一个很好的标准，用于识别可以用动态编程技术(如记忆化)优化的问题。

# 摘要

在本文中，我们讨论了如何使用动态编程来优化斐波那契数列问题。我们利用记忆化技术来消除递归函数调用带来的所有额外计算。

对于我们的解决方案，我们使用了被认为是[自上而下的方法](https://en.wikipedia.org/wiki/Top-down_and_bottom-up_design)，即将一个大问题分解成小问题。与这种方法相反的是一种[自下而上的](https://en.wikipedia.org/wiki/Top-down_and_bottom-up_design)方法，它从较小的简单问题开始，逐步解决较大的复杂问题。在本文中，我们没有讨论自底向上的方法，但是你可以在这里看到一个视频，展示如何实现斐波那契。

希望本文已经清楚地解释了动态编程对于优化我们的代码是多么有用，这样它就不会执行重复的任务和不必要的工作。下次你在解决像斐波纳契数列这样的问题时，想想如何用动态编程方法进行优化。

*更多内容请看*[***plain English . io***](http://plainenglish.io)