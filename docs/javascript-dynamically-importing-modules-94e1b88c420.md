# 在 JavaScript 中动态导入模块

> 原文：<https://javascript.plainenglish.io/javascript-dynamically-importing-modules-94e1b88c420?source=collection_archive---------6----------------------->

![](img/05349707e81e1766a8b26849c28e6953.png)

当涉及到开发有效的网站时，页面加载速度是至关重要的——特别是对于那些通过移动运营商的网络速度从移动设备访问的用户。2021 年，谷歌根据几个因素对网站进行排名——从累积布局变化到页面加载速度和未使用的 JavaScript，这些因素会使文件膨胀，减少加载时间和性能。通过努力减少脚本的数量和加载页面的时间，一个网站将在谷歌和其他搜索引擎上获得更高的分数，这反过来将帮助用户找到你的网站，并增加你的访客数量。

在现代 JavaScript 中，JS 文件可以被分解成多个更小的文件，组件可以只在需要时导出。这有助于缩短页面加载时间，并使您的代码库更容易管理和梳理，如果您或其他开发人员以后需要审查或重构它的话。下面是一个如何将 JavaScript 模块导入 JavaScript 的示例:

```
import User, { userDetail } from './Users.js'
```

这段代码将从名为“users.js”的 JavaScript 文件中导入名为 Users 和 userDetails 的模块。您可以根据需要将这些组件导入到其他模块化 JS 文件中。这称为静态导入，以这种方式导入模块的最大问题是，当包含这些代码时，浏览器会立即下载这些代码——这会导致页面加载非常缓慢，从而损害 SERP 评级，甚至会导致不耐烦的访问者尽可能远离您的站点。

在 JavaScript 中实现模块化导入的更好方法是使用动态模块导入。与静态模块导入非常相似，您可以仅在需要时导入某些模块——但是动态模块导入允许您仅在绝对必要时使用条件逻辑语句导入代码。这将导致更快的页面加载速度，因为浏览器不会试图立即下载所有的 JavaScript。如果用户不需要使用某个模块，它将不会被加载。

在 JavaScript 中有几种使用动态模块导入的方法。让我们看看从上面动态导入同一个模块:

```
import('./Users.js').then(({ default: User, userDetail }) => {
    //This will be the code that depends on the module...
});
```

这个方法非常类似于静态导入模块，但是这个导入是一个返回承诺的函数。这个承诺包含了这个模块的所有细节。您还会注意到，模块的默认导出必须根据承诺的返回值进行重构。这就是 default: User 的作用——它将模块的默认导出映射到用户变量。通过使用异步函数，可以进一步简化和清理这个导入函数。这里有一个例子:

```
const { default: User, userDetail } = await import('./Users.js');
```

这个方法的工作方式和 promise 函数完全一样，但是看起来更简洁，也更容易使用。

使用动态导入的模块有几个好处。我能想到的前三个原因是提高初始页面加载速度和避免不必要的浏览器填充。假设我们正在构建一个利用购物车功能的电子商务应用程序。购物车的逻辑相当复杂，因此需要大量代码才能运行。传统上，浏览器会立即下载所有这些代码，这会导致页面加载非常缓慢。然而，动态导入的模块可以解决这个问题，它允许我们在用户实际与购物车交互时只下载购物车的逻辑。

这里有一个例子:

```
addToCartBtn.addEventListener('click', async () => {
  const { showCart, checkout } = await import('./cart.js');
});
```

只有当用户单击“添加到购物车”按钮时，上述代码才会导入将功能添加到购物车所需的逻辑模块。通过这样做，购物车的代码直到绝对需要时才会被加载，这将为那些可能永远不会与购物车交互的访问者加快页面加载速度。

在许多应用程序中，可能有许多 polyfills，允许支持旧浏览器上的特性和功能。这些聚合填充会大大降低不需要它们的用户的页面加载速度，这无疑会影响访问者在现代浏览器上的用户体验。只有在需要时，我们才能使用动态模块来导入聚合填充:

```
if (isLegacyBrowser) import('./polyfills.js');
```

该导入没有返回值，因为当导入一个模块时，模块中的所有代码都会被导入，并且它们的聚合填充会在需要时自动设置。这样，可以实现一个函数，如果用户使用的是旧版本的浏览器，该函数将返回 true 值，然后 polyfills 模块将被导入。

另一名开发人员指出，在开发全球应用程序时，可能会有许多与国际化相关的文件和代码，为许多不同的语言提供支持和翻译。通过在初始加载时加载所有这些语言支持模块，浏览器将下载所有这些模块，这很可能会降低用户的页面加载速度。如果我们有一种方法，只在需要的时候导入国际化文件，甚至只导入用户特定语言需要的文件，那会怎么样？这是动态导入模块的另一个用途:

```
const userLang = window.navigator.userLanguage
|| window.navigator.language
const { localStrings } = awai import(`strings.${userLang}.js`);
```

这段代码允许浏览器根据用户的浏览器设置检测用户的首选语言，并只加载支持该语言所需的模块。

如您所见，动态导入的模块在 JavaScript 中非常有用。它允许更快的初始页面加载，防止浏览器下载未使用的代码，并提供更快、更好的用户体验。本文中的例子只是动态导入的模块可以做的一些令人惊奇的事情，但是我希望它能给你一些有用的建议，告诉你如何提高你的站点或应用程序的性能和排名。