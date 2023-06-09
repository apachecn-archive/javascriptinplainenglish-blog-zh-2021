# 每个测试人员都应该知道的 9 种软件测试

> 原文：<https://javascript.plainenglish.io/9-types-of-software-testing-every-tester-should-know-4841f647b73a?source=collection_archive---------10----------------------->

## 对**类软件测试的深入研究。**

![](img/4a27775168c5485a2a4f1ba1d7c622a2.png)

Photo by [National Cancer Institute](https://unsplash.com/@nci?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

没有无错误的软件。有些错误会在早期开发阶段暴露出来，而其他错误只在调试或销售之后才会出现。

在高级开发阶段，定位和修复源代码各自的问题可能会变得非常复杂和耗时。这就是软件测试以其多样性发挥作用的地方。

## 为什么是软件测试？

软件应用变得越广泛和复杂，连续测试就越有必要。熟练的软件测试能够及时识别和纠正错误，通过在项目管理方面实施合适的测试场景来支持更有效的故障诊断。

仅仅因为这个原因，开发团队应该在开发的同时考虑测试。作为软件的购买者，客户应该反过来询问开发团队，软件或其单独的模块将通过哪种方法进行测试。以下问题很重要:

*   开发者什么时候测试？也许在移交和验收前不久？
*   你有自己的软件测试团队吗？
*   是否有正在进行的测试？

# 软件测试分为四个基本测试类别

在软件测试中，完整的应用程序或其子组件应该经过至少四个测试类别:单元测试、集成测试、系统测试和最终用户测试。这些测试单元遵循一个系统化的结构，应该作为开发阶段的最低要求。

## 1.单元测试

一种基本的软件测试方法已经可以在早期开发阶段使用:单元测试。测试源代码的各个子组件或各个软件模块。为此，程序员编写自己的测试例程来检查函数是否没有错误。

优势显而易见——可以在早期阶段对单个组件进行详细测试；此时仍然可以在源代码中进行快速故障诊断。同时，可以实现源代码和测试代码的一致分离。

此外，可以为可重用性创建测试例程，这使得测试过程高效。顺便说一下，这影响到开发人员从一开始就应用了一个经过更仔细考虑和周密计划的程序。

## 2.集成测试

在单元测试的基础上，集成测试随之而来。不再按原样测试单个组件，而是测试它们的相互依赖性。

这个过程是软件测试的主要焦点之一——测试接口和整个过程的结果，以确保各个组件正确地协同工作。此时，易变内容转移中的错误或流程开发中的思维错误就暴露出来了。

集成测试的主要原因是定义的功能序列被运行，组件的相互依赖和它们的交互可以被检查。此外，不同开发团队之间的交流也得到改善。

## 3.系统试验

以下测试部分由系统测试组成。这里检查是否包含了软件的所有期望需求。此时，出现了处理规格表的经典案例。系统测试在预先确定的测试环境中进行，以检查所有功能性和非功能性要求是否存在，是否没有错误。

功能性需求与软件的实际功能相关，而非功能性需求与可用性、性能、操作可靠性和源代码的可维护性相关。

在大多数情况下，由于它们的抽象本质，非功能需求比功能本身更难测试。通常，测试环境是根据客户的生产环境建模的。

系统测试的主要优点是为客户接受产品做准备。此外，记录所有单个软件组件的主要工作可以在这个测试阶段完成。

## 4.最终用户测试

在基本测试的最后，是客户对软件的验收。在这里，客户自己测试最终产品。最终用户通常凭直觉进行测试，在支付最终发票之前，检查订购的所有功能是否都包括在内并且没有错误。

此时，客户行使他的权利来检查他所订购的东西是否已经实际交付。在大多数情况下，客户使用他们自己公司的数据进行测试，以模拟真实的生产过程。

顺便说一下，建议软件开发人员在他们的测试运行中也应该使用客户数据(或者至少是真实的数据)。一旦这个最终测试被成功通过，从法律的角度来看，合同就被履行了，软件就可以被视为交付和移交了。

# 软件测试的其他方法

软件测试可以在开发过程中通过其他特殊的测试过程来进行。下面是一些常用的方法:

## 5.回归测试

在这个过程中，一系列测试被反复重复，以确保已经测试过的组件不会导致新的错误。这些可能是通过修正从属子组件或维护和保养而产生的。

## 6.性能试验

顾名思义，对应用程序进行测试是为了确定它是否在对硬件资源(处理器、RAM、存储空间等)的最低要求下正常运行。).使用这种方法，通常有可能优化源代码以实现更快的功能过程。

## 7.大猩猩测试

使用这种方法，软件在其当前状态下经受残酷的测试，并且测试它的反应。所以 z. B .故意使用不正确的数据，并观察这是否会导致不一致。另一个选择是遍历所有可能的(和不可能的)键盘快捷键。典型的用户行为是，例如，在键盘上放置一个文件夹，并导致混乱的字符输入。

## 8.烟雾测试

这种测试形式通常用在早期的 alpha 阶段，甚至是在新版本发布之前。该测试包括基本功能，例如，b .也在用户界面中。测试现有功能的可操作性。如果测试失败，它不需要继续，因为很明显，在功能和非功能方面仍然存在基本错误。

## 9.安装测试

这里的目的是确定安装例程是否可以在所有预期的硬件和操作系统平台上正常运行。还会检查故意导致安装中止时的行为。

软件测试的主要目的是所有的功能和所有可能的数据值都必须在所有的组合中进行测试，这在实践中几乎是不可能的。因此，软件测试必须始终以用最少的测试用例获得尽可能广泛的测试覆盖为目标。

*更多内容尽在*[*plain English . io*](http://plainenglish.io/)