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



