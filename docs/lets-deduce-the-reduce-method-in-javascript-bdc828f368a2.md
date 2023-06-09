# 让我们推导一下 JavaScript 中的 Reduce 方法

> 原文：<https://javascript.plainenglish.io/lets-deduce-the-reduce-method-in-javascript-bdc828f368a2?source=collection_archive---------7----------------------->

![](img/fa36d827ceebe101729f0051af277f6c.png)

我学习 JavaScript 已经两年了，很快就熟悉了几乎所有的技巧——函数`map`、`filter`、`sort`等等。好吧，不撒谎，我在某些点上卡住了，但一些像样的解释在网络或 YouTube 上覆盖了这些主题，除了一件事——`reduce`方法。

然后我想知道为什么没有人像 JavaScript 中的其他方法一样自信地谈论`reduce`方法。这促使我深入研究它，弄清楚 JavaScript 中的 reduce 方法是什么、为什么以及如何使用的。在这 4 分钟的阅读之后，我向你保证的一件事是，你将更加自信地在你的代码中使用`reduce`方法。

## 那是什么呢？

Mozilla 文档将`reduce`方法定义为，

> `**reduce()**`方法在数组的每个元素上执行用户提供的“reducer”回调函数，并传入前一个元素的计算返回值。对数组的所有元素运行缩减器的最终结果是一个值”

乍一看这似乎很可怕，但让我们用通俗的术语来简化它。这是我对它的定义。

> " **reduce()** 方法从左到右遍历数组，对于每个元素，在给定现有值和计算新值的方法的情况下，计算下一个值。现有值是第一次迭代的初始值和所有其他迭代的前一次迭代的结果。它返回最终迭代的值作为结果”

我希望这张更清晰。reduce 方法的语法是，

```
arr.reduce(
   (accumulator, currentValue, index, array) => {}, // **callback function** 
   initialValue 
)
```

现在您已经看到了语法，让我们进一步分解我对`reduce`方法的定义。

*   它将遍历数组中的所有元素，就像`map`或`filter`方法一样。
*   它将根据我们提供的方法为每次迭代计算一个值。同样，与`map`或`filter`方法相同。这个方法就是我们所说的`callback`函数。
*   对于每次迭代，我们将在`callback`函数中获得前一次迭代的结果。这个结果将出现在回调函数的第一个参数中，即`accumulator`。
*   在第一次迭代的情况下，这个值将是我们作为第二个参数提供给`reduce`方法的`initialValue`。
*   回调函数的第二个参数是数组的当前元素，这个迭代是针对这个元素的。这同样类似于我们在回调`map`方法时得到的第一个参数。
*   最后一次迭代的结果就是我们从`reduce`方法中得到的结果。这里需要注意的一点是`reduce`返回一个单值。与`map`或`filter`方法不同，我们从 JavaScript 的`reduce`方法中获取单个值。
*   `index`和`array`是可选参数，其中索引是当前迭代元素的索引，就像`map`函数一样，数组是我们使用`reduce`方法的完整数组。

哇哦。这差不多就是 JavaScript 的`reduce`方法。拍拍自己的背，你已经成功了。

所以现在我们知道了`reduce`方法是什么。让我们看看如何使用它来编写一个整洁干净的 JavaScript 代码。

## 为什么减少？

利用我们对`reduce`方法的了解，我们可以重构很多代码。让我们从一个简单的例子开始。假设我们需要找到一个数组中所有元素的和。在了解`reduce`方法之前，我会这样做。

```
const arr = [1,2,3,4,5];
let sum = 0;
for (let i = 0; i < arr.length; i++) {
     sum += arr[i]; 
} 
console.log(sum); // 15
```

但那看起来很幼稚。这看起来不像现代的 JavaScript 代码，它是一个`for loop`。我现在是这样做的。

```
const sum = [1,2,3,4,5].reduce((a,c)=>a+c, 0);
console.log(sum); // 15
```

这看起来像 JavaScript。另外，注意在`for loop`代码中我们如何使用`let`来表示变量`sum`，但是在`reduce`方法中，我们可以使用`const`。

让我们再简化一点。我们的回调函数是`(a,c) => a+c`，非常简单。对于每一次迭代，我们将数组的当前元素`c`与前一次迭代的结果`a`相加。同样，我们的初始值是 0，这仅仅是因为没有数的和是 0。

好了，现在我知道了如何用 reduce 方法得到数组元素的和。让我们再向`reduce`迈进一步，计算一个数组中所有元素的平均值。我不会告诉你这个问题的`for loop`解决方案，因为你足够聪明，如果你一直呆到这里。让我们看看`reduce`对此的解决方案。

```
[10,20,10,5,5].reduce((a,c,i) => {
     a+=c;
     if(i===4) return a/5; 
     else return a;
}); // 10
```

在上面的例子中，我将当前元素添加到累加器中，然后检查这是否是最后一次迭代。如果是，我返回的是总和除以数组的大小。否则，我已经把钱还了。

如果你已经呆了这么久，给你一个临别提示。注意，在上面的例子中，我没有给我的方法`reduce`赋予初始值。这是一个可选参数，如果没有提供**，数组的第一个元素将作为初始值，迭代从第二个元素开始**。

这差不多就是 JavaScript 中的 reduce 方法。希望你今天学到了新东西。请务必查看这个空间，了解更多关于 JavaScript 的内容。

*让你内心的极客赢！*

*更多内容请看*[***plain English . io***](http://plainenglish.io/)