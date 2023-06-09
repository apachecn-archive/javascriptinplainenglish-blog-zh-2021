# 你应该知道的 30 种可怕的 JavaScript 速记技术

> 原文：<https://javascript.plainenglish.io/30-awesome-javascript-shorthand-techniques-that-are-good-to-know-6590545ced3d?source=collection_archive---------0----------------------->

## 使用这些速记技术来简化和优化您的 JavaScript 代码

![](img/e50fbb38872d8b07aa70c0b486328fff.png)

Photo by [Juan Gomez](https://unsplash.com/@nosoylasonia?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

任何编程语言中的速记技术都有助于您以更加简洁、优化和简短的形式编写代码。这些技术可以让你用更少的代码行编写代码，还可以帮你节省一些时间。现在，让我们一个接一个地复习一些速记技巧。

# 1.三元运算符

如果您只想根据条件给变量赋值，这是一个很好的选择。

您还可以向这个简写中添加一个等价的`else if`语句，如下所示。

# 2.分配默认值

如果你想给一个变量分配一个默认值，只要它是`null`或者`undefined`，你可以使用 nullish 合并操作符(`??`)来实现。

# 3.短路评估用？？

只有当左侧表达式返回除`null`或`undefined`之外的任何内容时，`??`操作符才会执行右侧表达式。

# 4.检查对象中是否存在属性

通常，当您使用`.`操作符访问一个对象中的属性时，如果它们中的任何一个没有被定义，那么就会抛出一个错误。当您使用`?.`操作符时，如果任何属性是`null`或`undefined`，操作符将返回`undefined`而不是抛出一个错误。

# 5.默认值包含？？=

该操作符类似于`??`并将进一步减少一个步骤。如果给定值为`null`或`undefined`，则`??=`检查会立即分配默认值，而不是用户单独分配值。

# 6.分配多个值

使用析构可以同时分配多个值。

> ***注意:*** 在对象析构的情况下，请确保变量名与该对象的属性名相同。您还可以使用别名来更改变量名，而不是默认的属性名，如下所示。

```
const { name: firstName, age:myAge } = person;
```

# 7.仅将所需的值赋给数组和对象中的变量

你也可以使用析构只分配需要的值。因为如果使用析构，元素/属性会分散开来，所以在处理数组时，会根据位置和对象的键名将值分配给左侧变量。

# 8.合并数组并向数组中添加多个元素

您可以合并两个不同的数组，也可以使用 spread 语法向现有数组添加新元素。

# 9.使用析构扩展语法

还可以使用带有析构的 spread 语法，将剩余的元素或属性一起赋给一个新变量。

# 10.用&和进行短路评估

如果您想仅在条件评估为除 falsy 值之外的任何值时执行函数，那么您可以使用带有`&&`的短路评估，如图所示。

> ***注意:*** 请注意，在 JavaScript 中，`*null*`、`*undefined*`、`*‘’*`、`*false*`、`*0*`的值为 falsy，其他值均为 truthy。

# 11.模板文字

如果您想将变量与静态字符串内容连接起来，您可以使用`+`操作符。当使用`+`操作符时，您需要自己管理空间。

您可以使用模板文字以更简单的方式实现同样的事情。

您也可以对多行字符串使用相同的方法。

# 12.Switch 语句的替代语句

可以使用函数名与键相关联的对象作为 switch 语句的替代。

# 13.对象属性分配

如果一个对象键应该与变量名相同，那么定义对象文字就可以用一种简单得多的方式来完成，如下所示。

# 14.箭头功能

如果一个函数嵌套在另一个函数中，可能会有点混乱。所以你可以利用箭头函数，用更简单更简短的方式来写它们。

# 15.隐性回报

在 arrow 函数中，如果您只有一个需要返回的语句，那么您也可以跳过花括号和`return`关键字。你可以用更简单的方式来写，如下所示。

# 16.对于循环

您可以使用`forEach()`，而不是使用传统的 for 循环来迭代数组元素。

如果您只想访问数组中的索引值或给定对象列表中的键，您可以使用一个`for…in`循环。

# 17.函数参数的默认值

以前，您使用 if 语句检查传递给函数的参数是否具有所有定义的值，并为它们分配一个默认值。您可以在函数声明本身中做同样的事情，如下所示。

# 18.声明变量

在作用域的顶部声明和分配变量是一个很好的做法。与其分别声明它们，不如用一种更短的方式来完成，这样既节省了时间，又减少了代码行数。

# 19.将对象值添加到数组中

# 20.查找数组中的元素

以前，如果您需要通过给定的条件在数组中找到一个对象，您可以使用一个`for`循环来迭代数组。你可以利用`find()`返回满足条件的对象。

# 21.字符串到数字的转换

您可以使用如下所示的`+`操作符以更简单的方式将字符串转换成数字。

# 22.多重条件检查

如果您需要使用`||`操作符检查 If 语句中的多个条件，那么您可以使用`includes()`来完成，如下所示。

# 23.交换变量值

不用使用临时变量来交换值，使用数组析构语法也可以很容易地做到这一点。

# 24.指数运算符

当你想提高一个给定数字的幂时，你使用`Math.pow()`。相反，您可以使用`**`以更简单的方式完成同样的操作。

# 25.获取字符串索引处的字符

# 26.强制参数

如果您想检查是否提供了强制参数，不使用`if`条件，您可以使用更短的方法，如下所示。

我们在这里所做的是在用户没有提供所需参数的情况下，给参数分配一个错误的默认值

# 27.十进制基数指数

如果一个数很长，末尾有多个零，那么可以用十进制指数格式来写这个数，如图所示。

# 28.使用！！

# 29.带~~的数的底值

你可以用`~~`代替`Math.floor()`以更快更简单的方式找到一个带小数点的数字的底值。

```
// Longhand
Math.floor(5.25) === 5 //true//Shorthand
~~5.25 === 5 //true
```

# 30.检查数组中项目的存在

如果你正在检查一个元素是否出现在一个数组中，你通常使用`indexOf()`。如果项目不存在，它返回`-1`，如果返回值大于`-1`，则项目可用。

一种简单的检查方法是使用`includes()`，如果元素存在，则返回`true`，如果没有找到，则返回`false`。

## 结论

这些是我发现非常有用的 30 种速记技巧。我希望当你在编码中使用它们时，你也会发现它们是有帮助的。

感谢阅读，祝学习愉快！

如果你喜欢阅读这样的故事，并且想支持我成为一名作家，考虑[注册成为一名媒体会员](https://nehalk.medium.com/membership)。每月 5 美元，让您可以无限制地了解 Medium 上的所有故事。如果你[通过我的链接](https://nehalk.medium.com/membership)注册，我会赚一点佣金。

[](https://nehalk.medium.com/membership) [## 加入我的推荐链接 media-Nehal Khan

### 作为一名中型会员，您的部分会员费将支付给您所阅读的作家，您可以完全接触到每个故事……

nehalk.medium.com](https://nehalk.medium.com/membership) 

*更内容于* [***通俗地说就是***](https://plainenglish.io/)

## 喜欢这篇文章吗？这里有一些你可能喜欢的其他文章

[](/how-does-javascript-actually-work-under-the-hood-567f9f17b855) [## JavaScript 实际上是如何在幕后工作的？

### JavaScript 引擎、事件循环、回调队列和 Web APIs 的概述。

javascript.plainenglish.io](/how-does-javascript-actually-work-under-the-hood-567f9f17b855) [](/12-javascript-concepts-that-every-good-web-developer-should-know-6fac820b507c) [## 每个优秀的网络开发人员都应该知道的 12 个 JavaScript 概念

### 有助于您成为更好的 JavaScript 开发人员的重要概念

javascript.plainenglish.io](/12-javascript-concepts-that-every-good-web-developer-should-know-6fac820b507c)