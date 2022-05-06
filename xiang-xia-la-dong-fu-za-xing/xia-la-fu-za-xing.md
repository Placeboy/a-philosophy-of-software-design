# 下拉复杂性

本章介绍了另一种思考如何创建更深层次的类的方法。假设你正在开发一个新的模块，而你发现了一种不可避免的复杂性。哪种方式更好：是让模块的用户来处理这种复杂性，还是在模块内部处理？如果复杂性与模块所提供的功能有关，那么第二个答案通常是正确的。大多数模块的用户多于开发者，所以开发者吃点苦头比用户吃点苦头要好。作为模块的开发人员，你应该努力让模块用户的生活尽可能轻松，即使这意味着你有额外的工作。表达这个想法的另一种方式是，**一个模块拥有一个简单的接口比一个简单的实现更重要。**

作为开发者，以相反方式行事的念头可能很具诱惑力：解决简单的问题并将困难的问题交给其他人。如果出现了你不确定如何处理的情况，最简单的方法就是抛出一个异常，让调用者来处理。如果你不确定要实施什么策略，你可以定义一些配置参数来控制策略，并让系统管理员来找出它们的最佳值。

像这样的方法在短期内会使你的生活更轻松，但它们会放大复杂性，使许多人必须处理一个问题，而不仅仅是一个人。例如，如果一个类抛出一个异常，这个类的每个调用者都必须处理这个问题。如果一个类导出了配置参数，那么每次安装中的每个系统管理员都必须学习如何设置这些参数。