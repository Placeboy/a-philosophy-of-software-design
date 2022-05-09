# 设计两次

设计软件是很难的，所以你对如何构造一个模块或系统的第一个想法不太可能产生最好的设计。如果你为每个主要的设计决定考虑多种选择，你最终会得到一个更好的结果：设计两次。

假设你正在设计一个将为GUI文本编辑器管理文件文本的类。第一步是定义该类将呈现给编辑器其他部分的界面；与其选择想到的第一个想法，不如考虑几种可能性。一种选择是面向行的界面，有插入、修改和删除整行文本的操作。另一个选择是基于单个字符插入和删除的界面。第三种选择是以字符串为导向的界面，对可能跨越行界的任意字符范围进行操作。你不需要确定每一种选择的每一个特征；在这一点上，勾勒出一些最重要的方法就足够了。

尽量选择那些彼此完全不同的方法；这样你会学到更多东西。即使你确定只有一种合理的方法，也要考虑第二种设计，不管你认为它有多糟糕。思考该设计的弱点，并将其与其他设计的特点进行对比，会很有启发。

在你粗略地设计出备选方案之后，把每个方案的优点和缺点列出来。对于一个界面来说，最重要的考虑因素是高层软件的易用性。在上面的例子中，面向线条的界面和面向字符的界面都需要在使用文本类的软件中进行额外的工作。面向线的接口需要更高级别的软件在部分行和多行操作中分割和连接线，比如剪切和粘贴选择。面向字符的接口将需要循环来实现修改一个以上的字符的操作。也值得考虑其他因素。一种选择是否比另一种选择有更简单的接口？在文本的例子中，所有的文本接口都是相对简单的。

一个接口是否比另一个更有通用性？

一个接口是否比另一个接口能更有效地实现？在这个例子中，面向字符的方法可能会比其他方法慢很多，因为它需要为每个字符单独调用文本模块。

一旦你比较了其他设计，你就能更好地确定最佳设计。最好的选择可能是其中的一个替代方案，或者你可能发现你可以将多个替代方案的特征结合到一个新的设计中，这个设计比任何一个原始选择都要好。

有时，没有一个备选方案是特别有吸引力的；当这种情况发生时，看看你是否能想出其他的方案。利用你在原始选择中发现的问题来推动新的设计。如果你在设计文本类时只考虑了面向线条和面向字符的方法，你可能会注意到每一个替代方案都很尴尬，因为它需要更高级别的软件来执行额外的文本操作。这是一个红旗：如果要有一个文本类，它应该处理所有的文本操作。为了消除额外的文本操作，文本界面需要与高层软件中发生的操作更紧密地匹配。这些操作并不总是对应于单个字符或单行。这条推理应该能让你找到一个面向范围的文本API，这就消除了早期设计的问题。&#x20;

两次设计原则可以应用于系统的许多层面。对于一个模块，你可以首先使用这种方法来选择接口，如上所述。然后，当你设计实现时，你可以再次应用它：对于文本类，你可以考虑一些实现，如行的链接列表，固定大小的字符块，或 "间隙缓冲器"。实现的目标将与接口的目标不同：对于实现来说，最重要的是简单和性能。在系统的更高层次上探索多种设计也是很有用的，比如在为用户界面选择功能时，或者在将系统分解成主要模块时。在每一种情况下，如果你能比较几个备选方案，就更容易确定最佳方法。

设计两次并不需要花费大量的额外时间。对于一个较小的模块，如一个班级，你可能不需要超过一两个小时来考虑替代方案。与你将花几天或几周时间来实施这个课程相比，这只是一小部分时间。最初的设计实验可能会产生一个明显更好的设计，这将足以支付两次设计的时间。对于较大的模块，你会在最初的设计探索中花费更多的时间，但是实现的时间也会更长，而且更好的设计带来的收益也会更高。

我注意到，两次设计的原则有时很难被真正的聪明人所接受。在他们成长的过程中，聪明人发现他们对任何问题的第一个快速想法就足以获得好成绩；没有必要考虑第二或第三个可能性。这使得他们很容易养成不良的工作习惯。然而，随着这些人年龄的增长，他们被提升到有越来越难的问题的环境中。最终，每个人都会达到这样一个地步：你的第一个想法已经不够好了；如果你想得到真正的好结果，你必须考虑第二种可能性，或者也许是第三种，不管你有多聪明。大型软件系统的设计就属于这种情况：没有人能够好到在第一次尝试时就把它做对。

不幸的是，我经常看到一些聪明人坚持实施他们想到的第一个想法，这导致他们不能发挥其真正的潜力（这也使他们在工作中感到沮丧）。也许他们潜意识里认为，"聪明人第一次就能做对"，所以如果他们尝试多种设计，就意味着他们毕竟不聪明。事实并非如此。并不是你不聪明，而是这些问题真的很困难！"。此外，这是一件好事：处理一个你必须仔细思考的困难问题，比处理一个你根本不需要思考的简单问题要有趣得多。

两次设计的方法不仅可以改进你的设计，还可以提高你的设计技能。设计和比较多种方法的过程会让你了解使设计变得更好或更坏的因素。随着时间的推移，这将使你更容易排除不好的设计，并磨练出真正伟大的设计。