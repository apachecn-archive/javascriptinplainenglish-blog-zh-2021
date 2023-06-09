# 学习 JavaScript 的有序方法:介绍和概述

> 原文：<https://javascript.plainenglish.io/a-sequenced-approach-to-learning-javascript-introduction-and-overview-b630956918b4?source=collection_archive---------18----------------------->

![](img/afec9dcbb2b0c5de2981ffb811bbbef1.png)

Photo by [Lagos Techie](https://unsplash.com/@heylagostechie?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

在教授如何使用编程语言时，计算机编程教师会使用几种不同的方法。一些老师开始向学生展示如何写“你好，世界！”编程，然后从那里展开。一些教师从介绍不同结构的语法开始

我想建议一种不同的技术，它遵循一种更结构化、更有序的方法。我将在本文中为您提供这种方法的概述，然后在后续文章中，演示如何使用这种方法学习 JavaScript。

在本文中，我将使用 Mozilla 的 Spidermonkey JavaScript。

# 学习编程的四个步骤

学习编程的第一步是学习如何阅读程序代码。如果一个学生不明白程序在做什么，就不能指望他写代码。教学生如何阅读代码的最好方法是让他们跟踪代码并更新变量的值。

代码跟踪，或者变量跟踪，应该被用来教授编程语言的每一个构造，从变量赋值语句，到分支语句，循环语句，甚至函数调用。下面我将提供代码跟踪的例子，以及其他步骤。

学习编程语言的第二步是用伪代码编写程序。这一步假设学生已经知道如何阅读和理解一个程序，并且能够把一个问题解决方案的类似英语的描述翻译成一个工作程序。

编程学习序列的第三步是学习理解问题解决模板。您可以将这些模板视为简单的算法，为常见问题提供结构化的解决方案。

第四步是让学生拿一个程序模板，并将其应用于一个独特的问题。这是计算问题解决的本质，并表明学生已经充分吸收了序列中的前三个步骤。

# 第一个示例—变量互换

为了演示如何在实践中使用这种结构化的顺序学习编程的方法，这里有一个学习如何交换两个变量的值的例子。

第一步是对包含变量交换的程序执行变量跟踪。程序如下:

```
let var1 = 12;
let var2 = 22;
let temp = var1;
var1 = var2;
var2 = temp;
```

要执行变量跟踪，请列出程序中的变量，后面跟着它们在程序结束前保持的值。下面是上面代码的跟踪结果:

var1: 12，22

var2: 22，12

温度:12

另一种方法是在程序中写入变量时，写出变量及其值，如下所示:

var1: 12

var2: 22

温度:12

var1: 22

var2: 12

然而，变量是写出来的，做一个跟踪并得到正确的结果表明学生理解程序在做什么。

下一步是能够用自然语言(伪代码)描述变量交换，并将其转换成 JavaScript 代码。以下是变量交换问题的伪代码:

*将 name1 的值设置为“Jane”
将 name2 的值设置为“Barb”
将 temp 的值设置为 name1
将 name1 的值设置为 name2
将 name2 的值设置为 temp*

这是这段伪代码生成的程序:

```
let name1 = "Jane";
let name2 = "Barb";
let temp = name1;
name1 = name2;
name2 = temp;
```

当学生能够成功地将伪代码转化为正确编写的程序时，学生就准备进入第三步——阅读解决问题的程序模板。

第三步是给学生一个实现模板的程序，让他们能够通过理解代码的功能来识别模板。例如，下面是变量交换的另一个例子:

```
let salary1 = 20000;
let salary2 = 23000;
let temp = salary1;
salary1 = salary2;
salary2 = temp;
```

已经掌握了学习过程的前两步的学生应该能够阅读这些代码，如果有必要的话也许可以跟踪它们，并且能够识别它是一个实现变量交换的程序。

然后，最后一步是给学生一个独特的问题，需要有问题的模板来找到正确的解决方案。下面是这样一个问题的例子:

辛西娅有两个手电筒。第一个手电筒有最好的光束，但它的电池非常弱，即将熄灭。另一个手电筒光线较弱，但电池很强。辛西娅需要写一个程序，模拟更换手电筒的电池，这样光束最好的手电筒就有最强的电池。

然后，学生必须编写一个 JavaScript 程序来最好地解决这个问题。这是一个充分计划的例子:

```
let flight1Batteries = "weak";
let flight2Batteries = "strong";
let flightTemp = flight1Batteries;
flight1Batteries = flight2Batteries;
flight2Batteries = temp;
```

至此，学生已经成功地展示了他们能够阅读解决特定问题的代码，根据伪代码描述编写代码，理解实现问题解决方案的程序模板，并使用程序模板解决独特的问题。该学生准备继续学习新的计划模板。

# 第二个示例—数字提取

在我的下一个例子中，我将演示一种向学生讲授分支、循环以及如何使用模数运算符的技术。此示例使用一个四位数作为 ID 号，其构造方式使得该数字的前三位数之和等于第四位数。例如，1237 是有效的身份证号码，因为 1 + 2 + 3 等于 7，但 1238 无效。

学生从学习如何使用模数运算符从一个数中提取每个数字开始这个例子。原则是，如果你取任何一个数的模 10，运算的结果将是当前在十位的数。例如:

```
print(1234 % 10); // displays 4
```

然后，如果将该数字除以 10，则该数字会减少该位数，如下所示:

```
let x = 1234;
let lastDigit = x % 10; lastDigit gets 4
x = parseInt(x / 10); x gets 123
```

这样继续操作，直到数字下降到只有一位数。

第一步是提供一些代码供学生跟踪，以确保他们理解模数运算是如何工作的。这里有一个例子:

```
let x = 324;
let last = x % 10;
x = parseInt(x / 10);
let second = x % 10;
x = parseInt(x / 10);
let first = x % 10;
x = parseInt(x / 10);
```

后续跟踪如下所示(变量显示多次):

x: 324

最后:4

x: 32

第二:2

x: 3

第一:3

x: 0

一旦学生能够使用模数运算符追踪几个数字提取的例子，他们就准备好继续编写数字提取代码了。以下是一个数字提取问题的伪代码描述:

*将数字设置为 5632
将最后一个数字设置为模数 10
将数字设置为整数除以 10
将第三个数字设置为模数 10
将数字设置为整数除以 10
将第二个数字设置为模数 10
将数字设置为整数除以 10
将第一个数字设置为模数 10
将数字设置为整数除以 10*

然后，学生需要将伪代码转换成可运行的 JavaScript 程序。他们可以一行一行地这样做:

```
let number = 5632;
let last = number % 10;
number = parseInt(number / 10);
let third to number % 10;
number = parseInt(number / 10);
let second = number % 10;
number = parseInt(number / 10);
let first = number % 10;
number = parseInt(number / 10);
```

你可能想知道为什么我在得到第一个数字后把数字除以 10，因为数字提取已经完成了。学生在学习循环时会再次遇到这个模板，而停止循环的循环条件是被提取的数字等于 0。

下一步是测试学生对数字提取模板的认识，向他们展示一个执行数字提取的独特程序，看他们是否能识别该程序正在做什么。一旦学生成功地做了几次，他们就准备好进入最后一步了。

在最后一步，给学生一个独特的问题，需要数字提取模板，并让他们编写代码来解决问题。这里有一个例子:

*Acme company 为其员工分配四位数字的 ID 号，其中 ID 的最后一位数字是一个校验位数字，它必须是前三位数字的总和。编写一个程序，将一个建议的 ID 作为输入，并确定该数字是否有效。*

这是解决这个问题的一个可能的方法:

```
putstr("Enter an ID number: ");
let number = parseInt(readline());
let id = number;
let checkDigit = id % 10;
id = parseInt(id / 10);
let third = id % 10;
id = parseInt(id / 10);
let second = id % 10;
id = parseInt(id / 10);
let first = id % 10;
id = parseInt(id / 10);
if (first + second + third === checkDigit) {
  print(number,"is a valid ID.");
}
else {
  print(number,"is not a valid ID.");
}
```

这个程序的最后一部分给学生一个机会来展示他们知道如何使用分支语句来确定 ID 号是否有效。

# 学习编程是一个循序渐进的过程

在他们的教育中，编程学生经常被要求过早地开始编写独特的、解决问题的程序。教授计算机编程应该遵循一个结构化的、顺序的过程，在这个过程中，学生被从一项技能引导到下一项技能。学生需要能够阅读代码，然后才能编写代码。学生需要理解程序模板(或算法)是如何工作的，然后才能实现它。通过遵循我在本文中概述的过程，学生将从一项技能转移到另一项技能，从而确保更好地理解编程过程。

# 后续步骤

在我的下一篇文章中，我将使用这个结构化的、顺序的过程来教读者如何声明数据并将数据赋给变量。

感谢您的阅读，请回复本文或给我发电子邮件，提出您的意见和建议。

*更多内容看*[***plain English . io***](http://plainenglish.io/)