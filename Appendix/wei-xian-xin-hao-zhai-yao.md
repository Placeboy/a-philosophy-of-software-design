# 危险信号摘要

下面是本书中讨论的一些最重要的危险信号。在一个系统中出现任何这些症状，都表明系统的设计存在问题。

**浅模块**：一个类或方法的接口并不比它的实现简单多少（见[4.5小节](../di-si-zhang-mo-kuai-ying-gai-shi-shen-de/4.5-qian-ceng-mo-kuai.md)）。

**信息泄露**：一个设计决策反映在多个模块中（见[5.2小节](../di-wu-zhang-xin-xi-yin-cang-ji-xie-lou/5.2-xin-xi-xie-lou.md)）。

**时序分解**：代码结构是基于操作的执行顺序，而不是基于信息隐藏（见[5.3小节](../di-wu-zhang-xin-xi-yin-cang-ji-xie-lou/5.3.md)）。

**过曝：**一个API迫使调用者了解很少使用的功能，以便使用常用的功能（见[5.7小节](../di-wu-zhang-xin-xi-yin-cang-ji-xie-lou/5.7-li-zi-http-xiang-ying-zhong-de-mo-ren-zhi.md)）。

**传递式方法**：一个方法除了将其参数传递给另一个具有类似签名的方法外，几乎什么都不做（见[7.1小节](../di-qi-zhang-bu-tong-de-ceng-bu-tong-de-chou-xiang/7.1-chuan-di-shi-fang-fa.md)）。

**重复**：一段不重要的代码被不断地重复（见[9.4小节](<../ch9 Better Together Or Better Apart?/9.4-fen-kai-de-tong-yong-dai-ma-he-te-shu-yong-tu-dai-ma.md>)）。

**特殊-普通混合体**：特殊用途的代码与普通用途的代码没有干净地分开（见[9.5小节](<../ch9 Better Together Or Better Apart?/9.5-li-zi-cha-ru-you-biao-he-xuan-ze.md>)）。

**连体方法**：两个方法有很多依赖关系，如果不了解另一个方法的实现，就很难了解一个方法的实现（见[9.8小节](<../ch9 Better Together Or Better Apart?/9.8-chai-fen-he-zu-he-fang-fa.md>)）。

**注释重复代码**：注释中的所有信息都可以从注释旁边的代码中一眼看出（见[13.2小节](../di-shi-san-zhang-zhu-shi-ying-gai-miao-shu-na-xie-zai-dai-ma-zhong-bu-ming-xian-de-dong-xi/13.2-bu-yao-zhong-fu-dai-ma.md)）。

**实现文档污染了接口**：接口注释描述了用户不需要的实现细节（见[13.5小节](../di-shi-san-zhang-zhu-shi-ying-gai-miao-shu-na-xie-zai-dai-ma-zhong-bu-ming-xian-de-dong-xi/13.5-jie-kou-wen-dang.md)）。

**含糊不清的名称**：一个变量或方法的名称非常不精确，以至于没有传达多少有用的信息（见[14.3小节](<../ch14 Choosing Names/14.3-ming-cheng-ying-dang-zhun-que.md>)）。

**难以取名**：很难为一个实体想出一个精确而直观的名字（见[14.3小节](<../ch14 Choosing Names/14.3-ming-cheng-ying-dang-zhun-que.md>)）。

**难以描述**：为了做到完整，一个变量或方法的文档必须很长。(见[15.3小节](<../ch15 Write The Comments First/15.3-zhu-shi-shi-yi-zhong-she-ji-gong-ju.md>)）。

**不易于理解的代码**：一段代码的行为或意义不能被轻易理解。(见[18.2小节](../ch18/18.2-shi-dai-ma-geng-bu-yi-yu-li-jie-de-dong-xi.md))。
