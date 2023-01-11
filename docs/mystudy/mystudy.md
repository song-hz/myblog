# 三维曲线

[MATLAB散点如何拟合三维曲线？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/54364417)

[(113条消息) matlab拟合空间曲线。散点拟合三维曲线_Aristotle__的博客-CSDN博客_空间曲线拟合](https://blog.csdn.net/Aristotle__/article/details/109490212?spm=1001.2101.3001.6650.1&utm_medium=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-109490212-blog-102744420.pc_relevant_vip_default&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2~default~BlogCommendFromBaidu~Rate-1-109490212-blog-102744420.pc_relevant_vip_default&utm_relevant_index=2)

[三维离散点进行曲线拟合 – MATLAB中文论坛 (ilovematlab.cn)](https://www.ilovematlab.cn/thread-295267-1-1.html?_dsign=f21b5197)

[(114条消息) matlab----三维曲面 (mesh 或者 surf) 上截取三维曲线(沿x轴方向，沿y轴方向，平行于xoy平面，对角线方向)_夜晓岚渺渺的博客-CSDN博客_matlab三维图截面提取](https://blog.csdn.net/kkxi123456/article/details/109126195)

[如何求两个曲面的交线？ - 知乎 (zhihu.com)](https://www.zhihu.com/question/545411646)

[(114条消息) 【1106matlab学习】在三维空间里绘制两个曲面的交线_Pumpkin720的博客-CSDN博客_matlab三维图形画曲面交线](https://blog.csdn.net/weixin_62784901/article/details/127714912)

[(114条消息) MATLAB | 一文解决各类曲面交线绘制，包含三维隐函数曲面交线_slandarer的博客-CSDN博客_matlab 两个曲面的交线](https://blog.csdn.net/slandarer/article/details/125710021?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-1-125710021-blog-127714912.pc_relevant_vip_default&spm=1001.2101.3001.4242.1&utm_relevant_index=4)

[Matlab三维曲线与曲面绘制教程 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/482212048)



# 模式识别

## 大作业

DSTC8 track2多轮对话回复选择

### 代码

- [TeddLi/DSTC_8_solution: This is our proposed model for subtask 1 and 2 of Dialog System Technology Challenges 8 (DSTC 8) (github.com)](https://github.com/TeddLi/DSTC_8_solution)
- [JasonForJoy/SA-BERT: CIKM 2020: Speaker-Aware BERT for Multi-Turn Response Selection in Retrieval-Based Chatbots (github.com)](https://github.com/JasonForJoy/SA-BERT) issue板块有作者问答和实验设定
- [wuningxi/tBERT: Code for the ACL 2020 paper 'tBERT: Topic Models and BERT Joining Forces for Semantic Similarity Detection'. (github.com)](https://github.com/wuningxi/tBERT)
- [LDA-BERT/model.py at master · maraja/LDA-BERT (github.com)](https://github.com/maraja/LDA-BERT/blob/master/model.py)
- [GitHub - jasonwu0731/ToD-BERT: Pre-Trained Models for ToD-BERT](https://github.com/jasonwu0731/ToD-BERT)
- https://github.com/taesunwhang/BERT-ResSel
- https://github.com/bearblog/text_matching

### 论文

- [2010.16407.pdf (arxiv.org)](https://arxiv.org/pdf/2010.16407.pdf) TopicBERT for Energy Efficient Document Classification

### 论文分析

- [(95条消息) 【论文笔记】Bert：Pre-training of Deep Bidirectional Transformers for Language Understanding_BodyCsoulN的博客-CSDN博客](https://blog.csdn.net/BodyCsoulN/article/details/121203376)
- [(95条消息) 论文翻译：TOD-BERT：任务导向型对话的预训练自然语言理解模型_深海木卫二的博客-CSDN博客](https://blog.csdn.net/weixin_42208219/article/details/113394325)
- [(95条消息) tBERT: Topic Models and BERT Joining Forces论文学习_HxShine的博客-CSDN博客_tbert](https://blog.csdn.net/qq_16949707/article/details/118418711)
- [融合主题做文本匹配](https://blog.csdn.net/qq_27590277/article/details/110848829)
- [ACL2020 | tBERT: 结合主题模型和BERT实现语义相似度分析 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/357635923)

### DSTC Track2 Result

[excel 表格结果](https://docs.google.com/spreadsheets/d/1GpJikalmFSb2EUVPdlM8g61pco8iqFgESFxlgMuMbGA/edit#gid=0)

### Bert学习

#### 【CLS】

[CLS]就是classification的意思，可以理解为用于下游的分类任务。

主要用于以下两种任务：

单文本分类任务：对于文本分类任务，BERT模型在文本前插入一个[CLS]符号，并将该符号对应的输出向量作为整篇文本的语义表示，用于文本分类，如下图所示。可以理解为：与文本中已有的其它字/词相比，这个无明显语义信息的符号会更“公平”地融合文本中各个字/词的语义信息。

BERT模型除了添加[CLS]符号并将对应的输出作为文本的语义表示，还对输入的两句话用一个[SEP]符号作分割，并分别对两句话附加两个不同的文本向量以作区分

#### cased和uncased的区别

cased区分大小写，不需要lower-case
uncased不区分大小写(这句话是错的，所谓不区分大小写实际上是不能区分大小写，因为词表只有小写)，需要lower-case
[https://blog.csdn.net/weixin_43301333/article/details/113967056](https://blog.csdn.net/weixin_43301333/article/details/113967056)转载

#### 结构图解

- [(95条消息) BERT原理和结构详解______miss的博客-CSDN博客_bert结构](https://blog.csdn.net/u011412768/article/details/108015783)
- [图解BERT模型：从零开始构建BERT - 腾讯云开发者社区-腾讯云 (tencent.com)](https://cloud.tencent.com/developer/article/1389555)
- [BERT的嵌入层是如何实现的？看完你就明白了 (qq.com)](https://mp.weixin.qq.com/s/DfIAuo775_sHGYi5z9IZyw)

#### bert topic

- [BERT如何融合主题模型-ACL2020 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/332248038)
- [基于BERTopic的交互式主题模型 - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/349781103)

#### 返回值

- [(95条消息) BERT模型返回值_乐清sss的博客-CSDN博客_bert返回值](https://blog.csdn.net/sunyueqinghit/article/details/105157609)

- [(95条消息) BERT 获取最后一层或每一层网络的向量输出_loong_XL的博客-CSDN博客_outputs.pooler_output](https://blog.csdn.net/weixin_42357472/article/details/120880899)

  

## 小作业

调研半监督学习理论

### 半监督学习问题和挑战

[半监督学习代码库存在的问题与挑战-电子发烧友网 (elecfans.com)](https://www.elecfans.com/d/1907010.html)

研究员们注意到目前大部分半监督论文**「只关注」**计算机视觉 (CV) 分类任务，而**「其他领域」**（例如自然语言处理 (NLP)、音频处理 (Audio)）研究者无法得知这些在CV任务上有效的算法是否依然有效。另外，大部分半监督论文都是由谷歌，微软等大型机构发表的，学术界的实验室往往由于计算资源的限制不能一起推动半监督领域的发展。总的来说，半监督学习基准目前存在以下两个问题：

（1）多样性不足。现有的半监督学习基准大多局限于计算机视觉 (CV) 分类任务（即 CIFAR-10/100，SVHN，STL-10 和 ImageNet 分类），**「排除了对自然语言处理 (NLP)、音频处理 (Audio) 等分类任务的一致和多样化评估，而在NLP和Audio中缺乏足够的标记数据也是一个普遍问题。」**

（2）耗时且对学术界不友好。现有的半监督学习基准（如TorchSSL）通常是耗时且不环保的，因为它需要通常从头开始训练深度神经网络模型。具体而言，使用 TorchSSL评估FixMatch[1]大约需要**「300」**个[GPU](https://www.elecfans.com/tags/gpu/)日。如此高的训练成本使得许多研究实验室（尤其是学术界的实验室或小研究团体）无法负担得起SSL的相关研究，从而阻碍了SSL的进展。

[USB](https://www.elecfans.com/tags/usb/): 任务多样化和对研究者更友好的新基准库

微软亚洲研究院的研究员们联合西湖大学、东京工业大学、卡内基梅隆大学、马克斯-普朗克研究所等机构的研究人员们提出了**「USB」**：第一个将**「视觉，语言，和音频」**分类任务进行统一的半监督分类学习基准。相比于之前的半监督学习基准(如TorchSSL)只关注少量视觉任务，该论文不仅引入更多样化的应用领域，还**「首次」**利用视觉预训练模型（Pretrained Vision Transformer）大大缩减了半监督算法的验证时间（**「从7000GPU时缩减至900GPU时」**），使得半监督研究对研究者、特别是小研究团体更友好。USB的相关论文已被国际[人工智能](https://bbs.elecfans.com/group_1143)顶会NeurIPS 2022接收。

**「USB提供的解决方案」**

那么，USB如何一次性解决当前半监督基准存在的问题呢？研究员们进行了如下的改进：

（1）为增强任务多样性，USB引入了5个CV 数据集，5个NLP数据集和5个音频数据集提供了一个多样化且具有挑战性的基准，从而能够对来自不同领域的多个任务进行一致的评估。下表提供了USB与TorchSSL的任务和训练时间等方面的详细对比。

（2）为提高训练效率，研究员们将预训练的Vision Transformer引入SSL，而不是从头训练ResNets。具体而言，研究员们发现在**「不影响性能」**的情况下使用预训练模型可以大大减少训练迭代次数（例如，将 CV 任务的训练迭代次数从100万步减少到**「20」**万步）。（3）为了对研究人员更加友好，研究员们开源实现了14种 SSL算法并开源了一个模块化代码库和相关的配置文件以供研究者轻松再现USB报告中的结果。为了快速上手，USB还提供详细的文档和[教程](https://www.elecfans.com/v/)。此外，USB还提供**「[pi](https://www.elecfans.com/tags/pi/)p包」**以供使用者直接调用SSL算法。研究员们承诺未来会在USB中不断加入新的算法（例如不平衡半监督算法等）和更多更具挑战性的数据集。

半监督学习通过利用大量无标签数据来训练更精确、更鲁棒的模型，在未来有着重要的研究和应用价值。研究员们期待通过USB这一工作，能够予力学术界和工业界在半监督学习领域取得更大的进展。

------------------------------------------------------------------------------------------------------------------------------

当标注的数据较少时模型训练容易出现过拟合，一致性正则化方法通过鼓励无标签数据扰动前后的预测相同使学习的决策边界位于低密度区域，很好缓解了过拟合这一现象，代理标签法通过对未标记数据制作伪标签然后加入训练，以得到更好的决策边界，而众多方法中，混合方法表现出了良好的性能，是近来的研究热点。

----------------------------------------------------------------------------------------------------------------------------------------

。从半监督学习的角度来看，半监督检测和半监督分类没有特别大的区别，自训练和一致性约束方案的训练范式基本相同，也都采用了强弱扩增的方法来进行扰动，目标检测任务更多的关注到检测任务本身的特点，针对类别不均衡、前背景均衡以及定位等问题做出相应的改进，并结合半监督学习方法提升学习性能，这些都是比较实际的改进方向，从扩增的角度来做的话个人感觉并不是特别能泛化到其他任务上。半监督分割任务也是类似，重点可以放在如何结合语义分割任务的特点对半监督方案进行改进优化。

----------------------

另外，从学界和工业界的角度来看的话，半监督方案又有一些差别，学界采用的教师学生模型其实还是同一个模型，而工业界由于没有计算量等限制，从提升半监督性能的角度来说的话训练一个超大的教师模型来预测伪标签指导学生模型学习更加实用简单，举例来说训练一个见过大量数据的 SwinTransformer 去预测伪标签指导 ResNet18 小模型训练，肯定比 ResNet18 来自己教自己更靠谱、性能提升更多，理论上来说只要教师模型性能足够高，这样的方式可以逼近全监督性能。这种情况下的训练类似于蒸馏方案，所以还有半监督蒸馏相关的研究。工业界落地需要考虑更多复杂的情况，比如 OOD 样本的影响、某个特定关注的指标等，这个时候半监督方案需要更多的集中在特定伪标签筛选策略上，强调的是某个任务场景下的专用性，这也和学界方案的通用性存在一定的gap

--------------------

在现实世界中并没有一个SSL算法在所有的数据集中都有好的表现，每一个SSL算法都有其优势，因为标签数据在现实世界中算少数，而且并不保证无标签数据总能对提升模型的性能有帮助。因此在解决实际问题的时候应该选择那些相符的算法。一般的，如果类产生良好的聚类数据，则生成混合模型的EM算法会是一个很好的选择；如果特征自然地分为两个或者多个冗余和独立的特征集，那么标准的Co-Training可能比较适合；如果已经使用了SVM，那么直推式的SVM是一个自然的选择。在所有的情况下，自我训练和CoBC都是使用的包裹 (Wrapper) 方法
原文链接：https://blog.csdn.net/qq_26822029/article/details/100579063

----------

除了UDA以外，其他模型的实验都集中在图像问题上。因此，在NLP的应用问题上，目前仍然有大量工作值得探索。

# 多媒体隐写

隐写project

## out-of-bag

out-of-bag (oob) error是 “包外误差”的意思。

它指的是，我们在从x_data中进行多次有放回的采样，能构造出多个训练集。根据上面1中bootstrap sampling的特点，我们可以知道，在训练RF的过程中，一定会有约36%的样本永远不会被采样到。

注意，这里说的“约36%的样本永远不会被采样到”，并不是针对第k棵树来说的，是针对所有树来说，36%的样本永远不会在任何一棵树的训练集中出现过。

那这36%的样本，就是out-of-bag (oob) data，包外数据。

用这个包外数据来做evaluation，就相当于用测试集来做evaluation。所以RF不需要再用测试集来做evaluation了。

`bootstrap sampling`是自主采样法，指的是有放回的采样。

`Bagging`是并行集成学习方法最著名的代表，他是基于`bootstrap sampling`做的有放回抽样，多次抽样后组成多组训练集，来训练多个模型。

[(100条消息) RandomForest中的包外误差估计out-of-bag (oob) error estimate_ybdesire的博客-CSDN博客_oob误差](https://blog.csdn.net/ybdesire/article/details/120375089)

[(100条消息) [隐写术\] J_UNIWARD介绍_Odinaris的博客-CSDN博客](https://blog.csdn.net/odinaris/article/details/93618395)

## 隐写指标

精确度/错误率/召回率/虚警率/漏检率

[隐写分析算法中的检测指标 - TracyCuiq - 博客园 (cnblogs.com)](https://www.cnblogs.com/keyky/p/12416589.html)

## SRM

[SRM(空域富模型隐写分析) - 梁君牧 - 博客园 (cnblogs.com)](https://www.cnblogs.com/lwp-nicol/p/15341092.html)

[(100条消息) SRM高维特征隐写分析原理与应用_jhon-ranble的博客-CSDN博客_srm特征](https://blog.csdn.net/Jhon_ranble/article/details/118786616)

## ROC

点绘制接收者操作特征曲线（Receiver Operating Characteristic curve,ROC曲线），该曲线下的面积AUC(Area Under the Curve of ROC)值可展示其检测性能。具体来看AUC值越大表示分类检测器的正确率越高，检测性能越好。

[(100条消息) 隐写术基础_唠嗑！的博客-CSDN博客_隐写术](https://blog.csdn.net/forest_LL/article/details/123953611)

# 人工智能



# 低欲望社会



