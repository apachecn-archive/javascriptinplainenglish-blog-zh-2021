# 为您的 Next.js 和 React 项目检验 9 项增强体验的技术

> 原文：<https://javascript.plainenglish.io/9-experience-enhancing-technologies-to-check-out-for-your-next-js-and-react-project-68bb56741f37?source=collection_archive---------8----------------------->

## 将您的项目带到下一个级别的库、框架和服务。

![](img/e0da6c231e26e8cf3a507663b3d9c267.png)

Photo by [Lagos Techie](https://unsplash.com/@heylagostechie) on [Unsplash](https://unsplash.com)

Next.js 本身就是一项伟大的技术，因为它提供了许多伟大的特性，使得创建快速和通用的 React 应用程序和网站变得容易。然而，JavaScript 生态系统的美妙之处在于有大量隐藏的(不那么隐藏的)珍宝，它们将增强您作为开发人员的体验和最终用户的体验。

在本文中，我将介绍 9 种技术，它们可以增强您的下一个 Next.js 项目的前端、后端和全栈开发，以及整体体验。

# 1.前端

## goober:CSS-in-JS 的一个较小的选择

React 生态系统因不同的样式选项而变得臃肿，可以说最流行的是 CSS 模块、情感和样式组件。

然而，这些选项的一个鲜为人知的竞争对手拥有与其他 CSS-in-JS 库相同的核心功能，与众不同的特征是它的大小:与 emotion 和 styled-components 分别为 11kB 和 12kB 相比，goober 的大小不到 1kB！

这将极大地减少你的网络应用的捆绑大小，并最终导致更快的加载时间和更好的用户体验。

在[https://github.com/cristianbote/goober](https://github.com/cristianbote/goober)查看项目。

## 预反应:一种快速、微小的反应方式

Preact 提供了与前面提到的库相同的优势:它提供了与其更受欢迎的竞争对手相同的核心功能，而占用空间小得多。

一起， [React](https://bundlephobia.com/package/react@17.0.2) 和 [React-DOM](https://bundlephobia.com/package/react-dom@17.0.2) 的包大小为 42.2kB(！)，而 Preact 的大小约为 4kB 的十分之一。Preact 提供了与 react 和 React-DOM 的直接兼容性，因此您可以在 Next.js 应用程序中轻松地用 React 替换 Preact。

在 https://preactjs.com 了解更多关于 Preact 的信息。

## 查克拉-用户界面:预先设计和高度可定制的用户界面组件

预制的 CSS 框架和组件库在 web 和移动设计领域越来越受欢迎，这是理所当然的。你不再需要雇佣设计师来创建视觉上吸引人、引人注目的应用程序和网站。

React 有许多可用的组件库，它们带有预设计的组件和样式，您可以使用它们来设计和编写您的应用程序，包括建立在 [bootstrap.css 库之上的](https://getbootstrap.com/) [Ant Design](https://github.com/ant-design/ant-design) 、 [Evergreen](https://github.com/segmentio/evergreen) 和 [React-Bootstrap](https://github.com/react-bootstrap/react-bootstrap) 。

然而，由于其无限的模块化和可定制性，Chakra-UI 在所有其他组件库中脱颖而出。它的组件从 [TailwindCSS](https://tailwindcss.com/) 和 [TailwindUI](https://tailwindui.com/) 之类的东西中获得灵感，你可以定制和调整它们，以匹配你想象的设计。

参见[https://chakra-ui.com](https://chakra-ui.com)的文件和示例。

# 2.后端

## nest . js:node . js 的通用 web 框架

就其本身而言，Next.js 提供了编写 lambda 函数来驱动应用程序后端的很好的选项。然而，默认的提供可能是有限的，特别是如果你的后端涉及比简单的 lambda 函数所允许的更复杂的逻辑。

Nest.js 是一个流行的框架，旨在用于构建复杂的服务器端应用程序，可以集成到 Next.js 中以结合两者的力量。

Nest.js 的灵感来自 Angular 的模块化，他们提供了[很棒的文档](https://docs.nestjs.com/)，有助于克服任何新框架带来的学习曲线。

访问他们在 https://nestjs.com 的官方网站。

**奖励**:关于如何将 Nest.js 集成到 Next.js 的例子，请关注西蒙·克诺特的伟大教程，网址为[https://simonknott . de/articles/Integrating-NextJS-with-nestjs . html](https://simonknott.de/articles/Integrating-NextJS-with-NestJS.html)。

## Prisma:面向未来的 ORM 和数据库客户端

Prisma 提供的特性极大地改善了开发人员使用 SQL 数据库的体验。

Prisma 提供了一种模式语言，允许您轻松定义将在数据库中表示的模型，以及 Prisma 数据库客户端。因为您创建的模式与 Prisma 客户机集成在一起，所以您可以实际地进行类型安全的查询和变异。

此外，Prisma 还提供了一种数据库迁移服务，可以根据预先存在的数据自动为您的数据库生成模式，并提供了一种数据库浏览器来查看和操作您的数据库。

通过 https://www.prisma.io 了解 Prisma 提供的更多功能。

## supabase:Firebase 的开源替代方案

Firebase 是后端即服务最受欢迎的选择之一，因为它拥有强大的功能集和庞大的社区和生态系统。

然而，通过使用 Firebase 或其主要竞争对手 AWS Amplify，您可能会不知不觉地成为供应商锁定的受害者，这将限制您以后发展和利用其他服务的能力。

另一方面，Supabase 是 Firebase 的完全开源的替代方案。Supabase 作为开源软件的优势在于，除了不会被锁定到 Google Cloud 或 aws 的生态系统中之外，它还会不断地被社区审计安全缺陷和漏洞。

在 [https://supabase.io](https://supabase.io) 查看 Supabase 项目。

# 3.全栈

## Blitz.js:构建在 Next.js 之上的全栈 React 框架

如前所述，Next.js 在后端开发方面提供的选项非常有限。Nest.js 当然可以单独在服务器端解决这个问题，但是如果你正在寻找一个集成前端和后端的更全面的解决方案，可以考虑 Blitz.js。

正如官方项目[网站](https://blitzjs.com/)、*所描述的那样，“Blitz 是一个包含电池的框架，其灵感来自 Ruby on Rails，构建于 Next.js 之上，具有“零 API”数据层抽象，消除了对 REST/GraphQL 的需求。”*

Blitz.js 的目的是能够将复杂的后端逻辑无缝集成到您的前端 React 应用程序中。Blitz.js 是一个相对固执己见的框架，这意味着你的应用程序的大部分文件和文件夹结构都是由框架的要求决定的；也就是说，Blitz.js 采用的结构将使您的代码组织有序，易于理解。

在[https://blitzjs.com](https://blitzjs.com)观看介绍视频，阅读 Blitz.js 的特性。

## SWR:实时更新而不牺牲 UX

正如 Phil Karlton 的名言所说，“在计算机科学中只有两件困难的事情:缓存失效和命名。”

Stale-while-revalidate，简称 SWR，试图解决这两个挑战中的第一个。这个术语起源于 [HTTP RFC 5861](https://tools.ietf.org/html/rfc5861) ，它描述了一种管理缓存失效和重新验证的策略。

Next.js 背后的团队开发的 React SWR 库描述了使用 SWR 的优势:*“使用 SWR，组件将不断自动获得一系列数据更新。并且用户界面将总是快速和反应性的。”*

在 Next.js 应用程序中使用 SWR，您可以通过自动更新来实现应用程序的实时体验。

在 https://github.com/vercel/swr了解更多关于 SWR 和反应 SWR 图书馆的信息。

## GraphQL + Apollo:提高 DX 和 UX

到目前为止，您可能已经听说了在后端 API 中实现 GraphQL 的好处。GraphQL 允许您通过调用 API 上的单个端点来轻松地查询和变更数据。

使用 GraphQL，您只接收您需要的数据，减少了从您的 API 发送的 HTTP 响应的大小，从而使您的应用程序更快。除了使用 [apollo-server-micro](https://www.apollographql.com/docs/apollo-server/v1/servers/micro/) 之外，还使用 Next.js API 路由，您可以轻松地实现与 apollo 客户端集成的 Next.js 应用程序的 GraphQL 后端。

在[https://github . com/vercel/next . js/tree/canary/examples/API-routes-graph QL](https://github.com/vercel/next.js/tree/canary/examples/api-routes-graphql)查看 Next.js `api-routes-graphql`示例

# 结论

这些技术中的每一项都有助于改进 Next.js 应用程序或网站的不同方面。希望你会对其中一些感兴趣，并考虑在你的下一个项目中使用它们！

如果你有任何其他建议，请在本文的评论中留下。

*更多内容请看*[***plain English . io***](http://plainenglish.io/)