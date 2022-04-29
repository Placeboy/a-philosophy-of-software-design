# 前言

80多年来，人们一直在为电子计算机编写程序，但关于如何设计这些程序或好的程序应该是什么样子的讨论却出奇的少。关于软件开发过程，如敏捷开发和开发工具，如调试器、版本控制系统和测试覆盖工具，已经有相当多的讨论。还有对编程技术的广泛分析，如面向对象的编程和函数式编程，以及设计模式和算法。所有这些讨论都很有价值，但软件设计的核心问题在很大程度上仍未被触及。David Parnas的经典论文 "On the Criteria to be used in Decomposing Systems into Modules "出现在1971年，但在随后的45年里，软件设计的技术水平并没有在这篇论文之外取得多大进展。

计算机科学中最基本的问题是问题分解：如何将一个复杂的问题分割成可以独立解决的部分。问题分解是程序员每天都要面对的核心设计任务，然而，除了这里描述的工作之外，我无法在任何一所大学中找到一门将问题分解作为中心议题的课程。我们教循环和面向对象的编程，但不教软件设计。

此外，程序员之间的质量和生产力存在着巨大的差异，但我们几乎没有尝试去了解是什么让最好的程序员如此出色，或者在我们的课堂上教授这些技能。我曾与几个我认为是伟大的程序员交谈过，但他们中的大多数人都难以阐明使他们具有优势的具体技术。许多人认为，软件设计技能是一种与生俱来的才能，是无法教的。然而，有相当多的科学证据表明，许多领域的杰出表现更多的是与高质量的实践有关，而不是与先天的能力有关（例如，见Geoff Colvin的《天赋被高估》）。

多年来，这些问题一直让我感到困惑和沮丧。我一直在想，软件设计是否可以被教授，我还假设，设计技能是区分伟大程序员和普通程序员的原因。我最终决定，回答这些问题的唯一方法是尝试教授一门关于软件设计的课程。其结果是斯坦福大学的CS190。在这门课上，我提出了一套软件设计的原则。然后学生通过一系列的项目来吸收和实践这些原则。这门课的教学方式类似于传统的英语写作课。在英语课上，学生使用一个反复的过程，他们写一个草稿，得到反馈，然后重写以进行改进。在CS190中，学生从头开始开发一个实质性的软件。然后，我们通过广泛的代码审查来确定设计问题，学生修改他们的项目来解决这些问题。这让学生看到他们的代码如何通过应用设计原则而得到改进。

我现在已经教了三次软件设计课，这本书是基于课堂上出现的设计原则而编写的。这些原则是相当高层次的，接近于哲学（"将错误定义为不存在"），所以学生很难理解这些抽象的想法。学生学习的最好方式是写代码，犯错误，然后看看他们的错误和随后的修正与原则有什么关系。

在这一点上，你很可能会想：是什么让我认为我知道关于软件设计的所有答案？说实话，我不知道。在我学习编程的时候，没有关于软件设计的课程，也没有导师教我设计原则。在我学习编程的时候，代码审查几乎是不存在的。我对软件设计的想法来自于编写和阅读代码的个人经验。在我的职业生涯中，我已经用各种语言编写了大约25万行代码。我所工作的团队从头开始创建了三个操作系统，多个文件和存储系统，基础设施工具，如调试器、构建系统和GUI工具包，脚本语言，以及文本、绘图、演示和集成电路的交互式编辑器。一路走来，我亲身经历了大型系统的问题，并尝试了各种设计技术。此外，我还阅读了大量由其他人编写的代码，这使我接触到了各种方法，有好有坏。

从所有这些经验中，我试图提取一些共同的线索，包括要避免的错误和要使用的技术。这本书反映了我的经验：这里描述的每个问题都是我亲身经历过的，每个建议的技术都是我在自己的编码中成功使用过的。&#x20;

我并不期望这本书成为软件设计的最终定论；我肯定有一些有价值的技术被我遗漏了，而我的一些建议从长远来看可能会变成坏主意。然而，我希望这本书能够开启一场关于软件设计的对话。将本书中的观点与你自己的经验进行比较，自己决定这里描述的方法是否真的能降低软件的复杂性。本书是一篇观点文章，所以有些读者会不同意我的一些建议。如果你确实不同意，请试着去理解原因。我很想听听那些对你有用的东西，那些不起作用的东西，以及你对软件设计可能有的其他想法。我希望接下来的对话能够提高我们对软件设计的集体理解。我将把我学到的东西纳入本书的未来版本中。

与我交流本书的最佳方式是向以下地址发送电子邮件：software-design-book@googlegroups.com

我有兴趣听到关于这本书的具体反馈，例如错误或改进的建议，以及与软件设计有关的一般想法和经验。我特别感兴趣的是那些令人信服的例子，我可以在本书的未来版本中使用。最好的例子能说明一个重要的设计原则，并且简单到可以用一两段话来解释。如果你想看看其他人在邮件地址上说了些什么，并参与讨论，你可以加入Google Group software-design-book。

如果由于某种原因，软件-设计-书的谷歌小组在未来应该消失，请在网上搜索我的主页；它将包含关于如何交流这本书的最新说明。请不要向我的个人电子邮件地址发送与书有关的电子邮件。

我建议你对本书中的建议持谨慎态度。总体目标是减少复杂性；这比你在这里读到的任何特定原则或想法都要重要。如果你尝试了本书中的一个想法，发现它实际上并没有减少复杂性，那么不要觉得有义务继续使用它（但是，一定要让我知道你的经验；我希望得到反馈，了解哪些方法有效，哪些方法无效）。

许多人提出了批评或建议，提高了该书的质量。以下人士对本书的不同草稿提出了有益的意见。Jeff Dean, Sanjay Ghemawat, John Hartman, Brian Kernighan, James Koppel, Amy Ousterhout, Kay Ousterhout, Rob Pike, Partha Ranganathan, Keith Schwartz, and Alex Snaps. Christos Kozyrakis建议用 "深 "和 "浅 "来形容班级和界面，以取代以前的 "厚 "和 "薄"，后者有些含糊不清。我很感谢CS190的学生；阅读他们的代码并与他们讨论的过程帮助我理清了关于设计的思路。
