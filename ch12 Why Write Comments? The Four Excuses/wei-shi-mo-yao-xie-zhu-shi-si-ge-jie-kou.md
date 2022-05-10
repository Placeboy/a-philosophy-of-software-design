# 为什么要写注释？四个借口

代码内文档在软件设计中起着至关重要的作用。注释对于帮助开发人员理解系统和高效工作是必不可少的，但注释的作用还不止于此。文档在抽象化方面也起着重要的作用；没有注释，你就无法隐藏复杂性。最后，**写注释的过程，如果做得正确，实际上会改善系统的设计。**相反，如果一个优秀的软件设计没有良好的文档，它的价值就会大打折扣。

不幸的是，这个观点并没有得到普遍的认同。有相当一部分的生产代码基本上没有注释。许多开发者认为注释是在浪费时间；还有一些开发者看到了注释的价值，但不知为何从来没有去写。幸运的是，许多开发团队认识到了文档的价值，而且感觉这些团队的流行度正在逐渐提高。然而，即使在鼓励编写文档的团队中，注释也常常被视为苦差事，许多开发人员不了解如何编写，因此所产生的文档往往是平庸的。不充分的文档给软件开发带来了巨大而不必要的阻力。

在这一章中，我将讨论开发人员用来避免写注释的借口，以及注释确实重要的原因。然后，[第13章](../group-1/di-shi-san-zhang.md)将描述如何写好注释，之后的几章将讨论相关的问题，如选择变量名称和如何使用文档来改进系统的设计。我希望这几章能让你相信三件事：好的注释能使软件的整体质量大为改观；写好注释并不难；以及（这可能很难相信）写注释实际上是很有趣的。

当开发者不写注释时，他们通常会用以下一个或多个借口为自己的行为辩护：

* “好的代码是自文档化的。”
* “我没有时间写注释。”
* “注释会过时并变得具有误导性。”
* “我所看到的注释都是毫无价值的；何苦？”在下面的章节中，我将逐一讨论这些借口。