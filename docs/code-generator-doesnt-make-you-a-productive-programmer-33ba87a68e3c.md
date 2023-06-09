# 代码生成器不会让你成为一个高效的程序员

> 原文：<https://javascript.plainenglish.io/code-generator-doesnt-make-you-a-productive-programmer-33ba87a68e3c?source=collection_archive---------8----------------------->

## 完全相反。

![](img/fa7057e7e4e68859a69a3d519edcd0d0.png)

Photo by [Alvaro Reyes](https://unsplash.com/@alvarordesign?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

我们正在进行一个大型项目，这个项目已经开发了好几年了。这个项目已经发布了很多版本，从商业角度来看，是相当成功的。

从技术角度来看，肯定有一些事情可以做得更好。然而，最大的问题是这个项目使用了普遍的代码生成过程。

这个代码生成过程基本上检索所有的数据库元数据。然后，它生成一个完整的数据访问层，一大堆覆盖整个 DAL 的自动化测试，一大堆形成数据驱动业务层的额外类(尽管仍然可以添加真正的业务逻辑)，再一次，一大堆覆盖数据驱动业务层的自动化测试。

现在，最初提出代码生成的人显然有着良好的意图。他们希望最大限度地提高开发人员的生产力，这样每个人都可以尽快实现所需的功能。这也是人们转向代码生成的原因:提高生产率。

然而，代码生成并不是这样做的好方法。不过，从短期来看，这肯定会提高生产率。但这要付出可怕的代价:巨额技术债务。

代码生成基本上是一种捷径。不幸的是，当涉及到开发软件时，每条捷径都会带来一些技术债务，迟早，你必须还清这些债务，否则就有膝盖被打碎的风险。

现在，如果你不推迟太久的话，在大多数情况下，你以一种快速的方式而不是从一开始就正确地实现某个特性所招致的技术债务是很小的，并且很容易偿还(显然，最好避免一开始就招致任何技术债务)。

生成一个庞大的代码库，然后到处使用这些代码，当项目已经开发了很长时间时，这种影响是无法恢复的。

如果您想对生成的代码进行重大修改，例如，减少与具体类的耦合，您可能会遇到困难。

在我们的例子中，您可以用生成的代码做的大多数事情都可以用多种方式来完成。因此，每一种可能的使用场景都至少在应用程序代码库中的某个地方被使用过。不只是在几个地方，而是几乎所有的代码库。

这使得对用于生成代码的模板进行修改变得不可能，这至少会在系统的某个地方引入编译器错误。不仅仅是几个，而是几百个。当然，你可以开始修理它们。然后，您可以开始在模板中进行下一次更改，导致数百个更多的编译器错误。

如果你不得不到处修改一点语法，那会很痛苦，但至少这不是你无法克服的。但是如果你想改变生成代码的行为，你就有大麻烦了。所有使用生成的代码的代码都期望发生某种行为。所以改变模板意味着改变很多真正的代码。

当你处于这种情况时，Michael Feathers(《有效使用遗留代码》的作者)甚至不能帮你。见鬼，即使是蝙蝠侠也会像一个受惊吓的女学生一样逃跑，基本上我们也是这么做的。所以我们决定暂时保留生成的代码和真正的代码，我们提出了一个新的架构(没有代码生成),我们将用它来开发新的功能。

只要我们有空间，或者我们需要做出重大的改变，旧的代码就会慢慢地迁移到新的架构中。当然，它并不完美，但完全从零开始是一种无论如何都没有多大商业意义的方法。你不能保证“新”系统会迅速赶上“旧”系统。

我认为这是一个很好的例子，说明了基于代码生成的方法会像大白鲨一样狠狠地咬你一口。

从长期来看，你在最初的生产力中获得的一切都会让你失去很多灵活性，这(也是从长期来看)最终会让你失去比你最初获得的更多的生产力。

请始终记住，代码生成通常是对一开始没有正确解决的问题的解决方案。

*更多内容看*[***plain English . io***](http://plainenglish.io/)