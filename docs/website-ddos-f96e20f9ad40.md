# 以下是如何保护网站免受 DDoS 攻击的方法

> 原文：<https://javascript.plainenglish.io/website-ddos-f96e20f9ad40?source=collection_archive---------9----------------------->

## 你应该知道这两种类型的攻击。

![](img/08a287e6a139c4391730529c61087cc6.png)

Source: [Pixabay](https://pixabay.com/de/illustrations/hacker-hacking-diebstahl-cyber-5027679/)

所谓的 **DoS** (拒绝服务)攻击试图让用户无法访问网站。这通过淹没网络或使服务器瘫痪来实现。

一次 **DDoS** (分布式拒绝服务)攻击几乎是一样的——但是攻击是从多个系统进行的。

这就是 DDoS 攻击如此有效的原因。

拦截 DoS 攻击并不困难——因为只有一个源 IP，来自它的数据包可以简单地丢弃。大多数时候，这是动态的。如果一个特定的系统发送太多的请求，就会有更多的请求被拒绝。

由于在 DDoS 攻击中，请求来自不同的来源，因此不容易区分它们，特别是如果参与攻击的各个系统本身只发送少量请求。

攻击者不能总是与真实用户区分开来，这使得 DDoS 攻击问题重重。

让我们看看这两种类型的 DDoS 是什么。那么，如何保护网站免受此类攻击呢？

# DDoS 攻击的两种类型

对应用层和网络层的攻击大致可以区分开来。这两层都源自 OSI 模型。

## 这就是他们的意思。

对网络层的攻击旨在使服务器的带宽过载。
因此，实际用户无法再访问该网站——它被关闭了。这样的攻击非常原始。简单的发很多请求就够了。

然而，用户总是发送许多简单的 GET 请求是不常见的。这就是攻击者更容易被这种类型的攻击抓住的原因。

更高级的是对应用层的攻击。为什么？

由于效率更高，DDoS 攻击者面临着一个巨大的挑战:他们必须有许多系统来实施攻击。

通常，这种攻击是由僵尸网络实施的。这些网络由黑客控制的计算机组成。然而，入侵许多计算机并用它们进行同步攻击并不容易。如果僵尸网络只发送静态页面的经典 HTTP 请求，网络服务器通常不会介意。

为了使这种攻击有效，僵尸网络中的每个系统都必须执行多个请求。但是，如果攻击者的行为不正常，这会导致 web 服务器丢弃他们的数据包。

要真正让 web 服务器屈服，需要使用一种不同的方法。
发送的不是消耗带宽的简单请求，而是更复杂的请求。这些 GET 和 POST 请求包含必须由后端处理的参数和查询。

从缓存或磁盘发送文件对服务器来说并不费力。验证一个复杂的请求，执行它，并可能访问一个数据库或 API 要昂贵得多。单次攻击的效率更高——因此僵尸网络中的每个系统都需要更少的请求。

对于更复杂的请求，也有更多可能的组合。同一个客户端可以发送不同的参数。对于网络服务器来说，检测不自然的行为也更加困难。

# 常见 DDoS 防护的工作原理

## 客户困惑

在我看来，最聪明的方法之一是所谓的客户难题。这些涉及客户端在被重定向之前必须解决的小计算任务。你自己可能也经历过这种情况——你想通过一个域访问一个网站，但首先被重定向到另一个页面。

在那里需要几秒钟，直到你最终到达你想去的地方。

阻止你的页面可能给了你的浏览器一个计算任务。DDoS 攻击只有在尽可能同时发生的情况下才会有效。然而，僵尸网络中的计算机通常完全不同。过去，著名的攻击已经发现了由笔记本电脑、智能手机和家用设备(IoT)组成的僵尸网络。

当所有这些设备首先必须解决一个大致相同的计算任务时，它们需要不同的时间来完成，这仅仅是因为它们的能力不同。

解决任务的不同速度确保了攻击不再真正同时发生——服务器可以一个接一个地处理请求。很聪明，不是吗？

## 浏览器指纹

DDoS 攻击不是成千上万的人同时在浏览器中打开一个网页。那太复杂了，而且不够同步。

僵尸网络里的电脑一般都是被黑的，主人并不知道这种滥用。所以请求很少是由浏览器发出的，而是由发送 HTTP 请求的脚本发出的。简单 Python 脚本的请求和浏览器的请求是可以区分的——发送的头是至关重要的。

此外，真正的浏览器可以执行 JavaScript。这也可以用于确定例如屏幕的尺寸。所以很容易区分真正的浏览器和基本的 HTTP 请求。如果 DDoS 攻击不是非常复杂，僵尸程序可以通过这种方式暴露。重点在于“复杂”——因为有办法让任何脚本看起来像一个真正的浏览器。

首先，HTTP 头可以自由选择。第二，可以冒充真实浏览器的工具越来越多。

## Web 应用防火墙

这种防火墙可以检查对 web 服务器的请求。在潜在危险客户的情况下，他们的 IP 可以被列入黑名单。但是防火墙如何检测攻击者呢？

在攻击网络层的情况下，攻击者通常会发送许多请求—很容易注意到他们不是真正的用户。这种对 web 服务器的请求通常造成的损害较小，因为它只是一个简单的 GET 请求。

因此，每个攻击者都应该发送几个请求，这被防火墙阻止了。

对于应用层的攻击，这就有点困难了。然而，发送大量带有例如参数的请求的系统可能会被注意到。应用层请求通常更有效，因为它需要更多的计算能力，所以僵尸网络中每个系统只需要几个(如果不是一个)请求就足够了。

## 但是如果我们攻击防守者呢？

这是我过去经常问自己的一个问题——例如，如果有人攻击 Cloudflare，会发生什么？

最终，云 DDoS 保护系统不会神奇地免受攻击。事实上，在 DDoS 攻击中，严格来说，首先受到攻击的是 Cloudflare 等服务阅读器。他们的工作是延迟攻击或暴露攻击者——大量的计算能力。

好消息是:Cloudflare 及其公司拥有强大的计算能力。该平台本身标榜自己能够抵御迄今为止的每一次重大攻击。哪里有足够的计算能力，哪里就没有停机时间。

服务提供商不仅可以通过积极的策略来帮助防止 DDoS 攻击。它们还可以像防弹背心一样，随随便便地挡住所有的子弹。

## 缓存资源

需要区分不同类型的网站。像 WordPress 这样的系统按需组装网站。内容从数据库加载，由 PHP 呈现，然后发送到客户端——这是一项巨大的计算工作。

从逻辑上讲，这样的系统可以用少得多的请求成功地攻击。但通常情况下，对每个请求的页面计算是不必要的。例如，在博客上，独特的内容不会出现在每个请求中。因此缓存呈现的页面是有意义的。大多数请求由超高速缓存提供服务，这使得服务器可以处理更多的请求。

## 使用 CDN

像 Cloudflare 这样的服务提供商不仅提供针对 DDoS 攻击的保护。特别是 Cloudflare，以其 CDN 而闻名，它也有助于阻止攻击。这个想法是，整个网站存储在 CDN 上，因此是静态的。为静态站点提供服务不需要太多的计算能力，正如我们刚刚了解到的那样，Cloudflare 已经足够了。因此，把一个网站放在一个好的 CDN 上实际上是没有意义的——服务器会处理负载。

感谢您的阅读！

## [加入我的时事通讯，了解最新消息](http://eepurl.com/hacY0v)