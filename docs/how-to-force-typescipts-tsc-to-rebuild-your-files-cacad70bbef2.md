# 如何强制 TypeScript 的 tsc 重建您的文件

> 原文：<https://javascript.plainenglish.io/how-to-force-typescipts-tsc-to-rebuild-your-files-cacad70bbef2?source=collection_archive---------7----------------------->

![](img/5537196c6ea0d09f417f25eb1450d158.png)

我注意到在观察模式下使用`tsc`时，有时——特别是当一个文件被重命名时——它并没有意识到文件需要重新编译。这种状态会持续到重启，重启监视器，所有常见的事情。

我最后一次遇到这种情况是在我需要重新排序这个项目使用的种子文件的时候。一个最后需要放在第一位的文件，所有东西都必须移动，因为我在文件名中使用了数字，以确保播种顺序清晰。大多数情况下，它工作得很好。

重命名文件不成问题，但是突然之间,`lib/seeds`目录中有了两组种子。正如你所料，结果并不好。

`rm lib/seeds/*`，重新运行，然后……什么都没有。嗯。

也许需要提示来重新编译它们？`touch src/seeds/*`仍然一无所获。

上次发生这种情况时，我重启了笔记本电脑和一切。这一次，谢天谢地，我还没走到那一步就想起来了。

我找到的唯一解决办法？删除`tsconfig.tsbuildinfo`并重建。从文件名来看，我认为它似乎在那个文件中缓存了构建信息，这完全合理。它并不总是能判断出缓存何时过期。

希望这样可以节省一些重启和时间。

*更多内容尽在*[*plain English . io*](http://plainenglish.io/)