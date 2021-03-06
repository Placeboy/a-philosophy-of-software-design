# 在一起更好还是分开更好？

软件设计中最基本的问题之一是：给定两个功能，它们应该在同一个地方一起实现，还是应该将它们的实现分开？这个问题适用于系统中的所有层，如函数、方法、类和服务。例如，缓冲应该包含在提供面向流的文件I/O的类中，还是应该放在一个单独的类中？HTTP请求的解析应该完全在一个方法中实现，还是应该分给多个方法（甚至是多个类）？本章讨论了做出这些决定时需要考虑的因素。其中一些因素已经在前几章中讨论过了，但为了完整起见，这里将重新讨论一下。

在决定是合并还是分离时，目标是降低整个系统的复杂性，提高其模块化程度。看起来，实现这一目标的最好方法是将系统分成大量的小组件：组件越小，每个单独的组件就可能越简单。然而，细分这一行为会产生额外的复杂性，而这些复杂性在细分之前是不存在的：

* 有些复杂性仅仅来自于组件的数量：组件越多，就越难跟踪它们，也越难在庞大的集合中找到一个想要的组件。细分通常会导致更多的接口，而每一个新的接口都会增加复杂性。
* 细分可能会导致需要额外的代码来管理组件。 例如，在细分之前使用单个对象的一段代码现在可能必须管理多个对象。
* 细分会产生分离：被细分的组件会比细分前相距更远。 例如，在细分之前一起在一个类中的方法，在细分之后可能在不同的类中，并且可能在不同的文件中。分离使开发人员更难在同一时间看到这些组件，甚至更难意识到它们的存在。如果这些组件是真正独立的，那么分离是好的：它允许开发者在同一时间内专注于一个组件，而不被其他组件所干扰。另一方面，如果组件之间存在依赖关系，那么分离就不好了：开发人员最终会在组件之间来回切换。更糟糕的是，他们可能不知道这些依赖关系，这可能会导致错误的发生。
* 细分会导致重复：细分前存在于单个实例中的代码可能需要存在于每个细分的组件中。

如果代码片段是密切相关的，则将它们组合在一起是最有益的。 如果这些代码是不相关的，它们最好分开。这里有一些迹象表明两段代码是相关的：

* 它们共享信息；例如，这两段代码可能都依赖于某种特定类型的文档的语法。
* 它们是一起使用的：任何使用其中一段代码的人都可能会使用另一段。这种形式的关系只有在它是双向的情况下才有说服力。举个反例，磁盘块缓存几乎总是涉及哈希表，但是哈希表可以在许多不涉及块缓存的情况下使用；因此，这些模块应该是分离的。
* 它们在概念上是重叠的，因为有一个简单的更高层的类别，包括这两块代码。例如，搜索子串和大小写转换都属于字符串操作的范畴；流量控制和可靠交付都属于网络通信的范畴。
* 如果不看另一块代码，就很难理解某一块代码。

本章的其余部分使用了更具体的规则以及例子来说明什么时候把代码段放在一起有意义，什么时候把它们分开有意义。&#x20;
