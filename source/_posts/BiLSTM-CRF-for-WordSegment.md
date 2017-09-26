---
title: BiLSTM+CRF实现分词、命名实体识别、词性标注
date: 2017-09-14 17:31:08
categories:
- NaturalLanguage
tags:
- NaturalLanguage 
- DeepLearning
- LSTM
---
# Task
* 清楚英文的实现，使用tensorflow
* 扩展到中文分词

话不多说，先看papers：
#  References
## [1]Bidirectional LSTM-CRF Models for Sequence Tagging. 2015
[Read Full PDF](https://arxiv.org/pdf/1508.01991)  
### 摘要
　　基于序列标注提出的变种LSTM模型，这些模型包括LSTM，BI-LSTM（双向LSTM），LSTM结合CRF（条件随机场）层，bi-LSTM结合CRF层。

