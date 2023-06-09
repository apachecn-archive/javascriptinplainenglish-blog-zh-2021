# 如何用 JavaScript 构建二叉查找树

> 原文：<https://javascript.plainenglish.io/how-to-build-a-binary-search-tree-in-javascript-13218a160dc7?source=collection_archive---------12----------------------->

![](img/a37db9cdc02674cc40162aad9ee99d6d.png)

Photo by [veeterzy](https://unsplash.com/@veeterzy?utm_source=medium&utm_medium=referral) on [Unsplash](https://unsplash.com?utm_source=medium&utm_medium=referral)

数据结构就在我们周围，但除非你是软件工程师或数据科学家，否则你通常不会注意到它们。数据结构是计算机编程和处理数据的基础。对数据结构及其内部工作原理的深刻理解对于在这些领域取得成功至关重要，因此花时间详细了解它们是非常有益的。

# 二叉查找树(夏令时)

一个二叉查找树是一个[树形数据结构](https://en.wikipedia.org/wiki/Tree_(data_structure))和[二分搜索法算法](https://en.wikipedia.org/wiki/Binary_search_algorithm)的组合。数据以一种有利于二分搜索法的方式严格地组织在树形结构中。虽然使用这种结构有一些限制，但在某些情况下，BST 是当前任务的最佳选择。我们稍后将深入探讨这一点。

首先，我们需要建立一个心智模型。在钻研效率或代码之前，有一个完全成型的心智模型是很重要的。因此，让我们来看看搜索在 BST 中是如何工作的。

![](img/c646055ed985f25f3a201739d32095fa.png)

An illustration of a search in a binary search tree

该图显示了算法如何在 BST 中搜索值`60`。每次迭代搜索的值比较显示在顶部。底部的 BST 插图在每次迭代中都会更新，以显示当前的比较节点(用虚线边框显示)和已经排除的节点(用删除线文本显示)。

二分搜索法比你的典型搜索更优雅一些，因为它利用了数据组织的优势。就像在字典或词汇表中搜索单词一样，你不会只从第一页开始，一页一页地翻，直到找到你要的单词。相反，你可以把书大致翻到你认为单词可能是按字母顺序排列的地方，将你的单词与页面上的一个单词进行比较，看看你的单词是在前面还是后面，然后利用这些知识跳到应该更接近你的目标单词的另一页。一旦你到了一个非常接近的页面，你可以开始翻页，这样你就不会超出你的页面估计。

> 数据的组织方式是左子值总是小于父值，右子值总是大于父值。

二叉查找树以同样的方式工作。在每一次迭代中，您比较您的值，如果它们不相等，您将删除树中目标值不存在的那一半。这都是可能的，因为数据是这样组织的，左边的子值总是小于父值，右边的子值总是大于父值。因此，如果您知道您的值大于当前节点处的值，您可以排除左边的子节点及其所有后代。

正如我之前提到的，这种设计有一些有用的效率特征，我们将在接下来讨论。

# 效率

消费数据结构而不了解它们的效率就像普通人使用菜刀一样。你可以用牛排刀切苹果，但有些刀更适合这项工作。要知道用哪把刀，你需要知道每把刀的设计用途。类似地，要知道使用哪种数据结构，您需要了解它们的效率。

要理解一个数据结构的效率，你必须知道表达效率的语言。这种语言被称为[大 O 符号](https://en.wikipedia.org/wiki/Big_O_notation)，通常用于工程、数据科学和数学。此外，单个数据结构的效率在孤立的情况下并不特别有用。只有当你将它们相互比较时，它们才真正变得有用。当你学习数据结构和它们的效率时，你可以参考这个[备忘单](https://www.bigocheatsheet.com/)，我发现它在过去很有帮助。

现在当我们讨论数据结构效率时，我们通常只从时间复杂度的角度来讨论。这是因为大多数数据结构具有线性空间复杂度(即`O(n)`),所以比较它们是相当简单的。此外，我们通常只会对最坏的情况感兴趣，因为典型的情况通常不会使我们的机器资源过度紧张。

然而，在我们需要经常搜索项目的情况下，BST 特别适合这样做。特别地，对于一般情况，BST 具有`O(log(n))`时间复杂度。这意味着有时你可能会搜索一个位于树末端的元素，单次搜索的时间复杂度是`O(n)`，但是因为在每次迭代搜索中有一半的树元素被删除，所以典型的时间复杂度不是线性的。

现在有另一种数据结构具有更好的搜索时间复杂度，那就是哈希表。但是，二叉查找树更适合于数据与其相邻数据的关系很重要的情况。如果需要获得相邻的数据点或数据范围，使用 BST 可能比哈希表更好。

# 用 JavaScript 实现

一般来说，要实现一个二叉查找树，你需要实现一个节点来表示你的树中的每一个元素。BST 中的节点需要支持`value`、`left`和`right`属性。`left`和`right`属性是指向遵循 BST 刚性结构的子节点的指针。具体来说，`left`节点的`value`必须小于其父节点的`value`，并且`right`节点的值必须大于其父节点的`value`。下面是一个`Node`的类实现。

A class implementation of a binary search tree node in JavaScript

这个类非常简单。您必须用一个值实例化您的类，并且您也可以选择最初指定`left`和`right`节点。

现在我们有了我们的`Node`类，我们可以在我们的`BinarySearchTree`类中使用它来构建我们的功能。我们的`BinarySearchTree`类将有一个`insert`方法向树中添加一个节点，还有一个`contains`方法检查 BST 当前是否已经有了那个值。此外，我将向您展示如何通过这个 BST 实现一个[深度优先遍历](https://en.wikipedia.org/wiki/Depth-first_search)和一个[宽度优先遍历](https://en.wikipedia.org/wiki/Breadth-first_search)。虽然这并不是这个练习的全部必要条件，但是看看这些遍历是如何工作的，对于你全面理解二分搜索法树是如何工作的可能是有帮助的。

让我们来看看代码:

A class implementation of a binary search tree in JavaScript

现在，让我们更详细地分解这个类的每个部分。

**建造师**

`BinarySearchTree`类本身主要充当`head`节点的外壳。我们需要保持对我们的`head`的引用，因为我们树中的每一个其他节点都源自那个节点。因此，如果我们想在树中插入一个新节点，我们必须从`head`开始，因为它决定了所有其他节点的位置。我还选择用一个空的`Node`实例的默认赋值来提供这个值。这样，我可以依赖于存在一个头节点，而不必围绕它进行防御性编码。

**插入()方法**

`insert`方法对于任何二叉查找树都是至关重要的方法，因为每个节点都必须遵守严格的顺序。记住，`left`节点的值必须小于其父节点的值，而`right`节点的值必须大于其父节点的值。

至于算法，挺简单的。我们使用一个`while`循环遍历树，直到没有要检查的节点。在每次迭代中，我们将要插入的值与当前节点的值进行比较。这告诉我们继续穿越哪一侧，是`left`还是`right`。然后，如果在那一侧没有子节点(即`left`或`right`是`null`，我们将插入一个带有新值的新节点。否则，如果那里有一个子节点，我们将把它设置为新的当前节点，循环继续。

**包含()方法**

该方法检查`BinarySearchTree`实例是否包含提供的`value`参数。这里的逻辑和`insert()`类似，只是简单一点。我们仍然使用`while`循环遍历树，并将目标`value`与当前节点`value`进行比较。然而，我们现在只需要比较值是否相等，而不是寻找树的末端(也称为“叶”节点)以便在那里插入新节点。我们继续遍历，直到找到目标值或用完所有节点。

**depthfirstroversal()方法**

正如我前面提到的，这个方法并不是真正必要的，但是我发现将其与`breadthFirstTraversal()`方法进行比较是有帮助的，所以我添加了它。由于我们的`contains()`方法在技术上已经实现了深度优先遍历，我决定使用递归来实现这个方法，而不是我在`contains()`中使用的迭代方法。

递归可能是一个很难概念化的概念，所以如果你在理解它时有困难，看看这个视频[吧，我发现它很有帮助。否则，方法相当简单和简洁。该方法接受两个参数:每次迭代时调用的回调和起始节点。回调有一个默认赋值，本质上相当于](https://youtu.be/k7-N8R0-KY4)[一个“无操作”函数](https://en.wikipedia.org/wiki/NOP_(code)#JavaScript)，起始节点默认为`head`节点。从那里，我们简单地用当前传入的`value`调用我们的回调，然后分别用`left`和`right`节点递归调用我们的方法，如果它们存在的话。

**breadthfirstroversal()方法**

类似地，我添加了这个方法作为额外的奖励，来说明如何使用广度优先策略遍历一棵树。广度优先搜索不如深度优先搜索直观，但是有了合适的心智模型，逻辑就相当简单了。首先，让我们来说明我们的过程。

![](img/25f8ee24cf1917310d2d4b29aa189563.png)

An illustration of breadth-first search in a binary tree

上图显示了我们如何在移动到下一行之前完全遍历每一行。相反，使用深度优先遍历，我们在移动到下一个分支之前遍历整个分支。

有几种不同的方法来设计这个算法，但总的思路是遍历树，并沿着树的方向，按照需要的顺序放置对每个节点的引用。然后，您可以简单地遍历您的有序引用。如上所述，我们首先完全遍历每个“行”，然后继续下一个“行”。因此，我们将为每个“行”运行这个子例程。在我的解决方案中，我们将使用队列对每个节点的引用进行重新排序，然后当我们将它们出队时，它们将按正确的顺序从队列中删除。

如果您对队列数据结构不熟悉，请查看我写的这篇文章[详细描述了它们，并向您展示了如何用 JavaScript 构建一个`Queue`类。](/how-to-build-a-queue-in-javascript-c2652500e82d)

# 结论

二叉查找树是一种独特的数据结构，其设计考虑了搜索效率。希望这篇文章对你有用，如果有用，请给我一个关注，这样当我发布更多内容时，你会第一个知道。谢谢！

*最初发表于*[*【https://codingbootcampguides.com】*](https://codingbootcampguides.com/how-to-build-a-binary-search-tree-in-javascript)*。*

*更多内容请看*[***plain English . io***](http://plainenglish.io/)