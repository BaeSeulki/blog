---
title: 朝花不可夕拾
categories:
- Knowledge
tags:
- MachineLearning
- DeepLearning
- NaturalLanguage
date: 2017-09-12 19:28:21
---
* * *
**本文长期更新，用于记忆一些知识碎片，主要以简介和链接的形式展示。**
* * *
# Natural Language Models
## Variational Autoencoders
> **keywords:** 
> 自编码器、生成模型、非监督学习

### ***About***
VAE is the state-of-the-art generative model, another is GAN.
### ***Related Papers***  
1. [Tutorial on Variational Autoencoders](https://arxiv.org/pdf/1606.05908.pdf)  
  
	> 	This tutorial introduces the intuitions behind VAEs, explains the mathematics behind them, and describes some empirical behavior. No prior knowledge of variational Bayesian methods is assumed.

### ***Related Blogs*** 
1. [what is variational autoencoder](https://jaan.io/what-is-variational-autoencoder-vae-tutorial/)  

	> 	Understanding Variational Autoencoders (VAEs) from two perspectives: deep learning and graphical models.  
2. [VAE在NLP领域的应用](http://rsarxiv.github.io/2017/03/02/PaperWeekly%E7%AC%AC%E4%BA%8C%E5%8D%81%E4%B8%83%E6%9C%9F/) From PaperWeekly 
 
	> * 《[Generating Sentences From a Continuous Spaces](https://aclweb.org/anthology/K/K16/K16-1002.pdf)》. ICLR 2016  
	> * 《[Neural Variational Inference for Text Processing](https://arxiv.org/pdf/1511.06038.pdf)》. ICML 2016  
	> * 《[Language as a Latent Variable: Discrete Generative Models for Sentence Compression](https://arxiv.org/pdf/1609.07317v1.pdf)》. EMNLP 2016
	> * 《[A Hierarchical Latent Variable Encoder-Decoder Model for Generating Dialogues](https://arxiv.org/pdf/1605.06069.pdf)》. AAAI 2017
	> * 《[Variational neural machine translation](https://arxiv.org/pdf/1605.07869.pdf)》. EMNLP 2016
	> * 《[A Hybrid Convolutional Variational Autoencoder for Text Generation](https://arxiv.org/pdf/1702.02390.pdf)》  
3. [Applications of Autoencoders in Natural Language Processing](https://www.doc.ic.ac.uk/~js4416/163/website/nlp/)
	> Autoencoders for Representation and Deep Learning;  
	> Applications in Natural Language Processing;  
4. 来自知乎的
	> * [知乎里的理解 From Gerry Che](https://zhuanlan.zhihu.com/p/21741426)  
	VAE本质上不是一个deep generative model. 因为它实质上只是学习一个两层的graphical model. 
	> * [知乎学术兴趣小组：VAEs](https://zhuanlan.zhihu.com/p/25401928)
   
    
### ***Github Projects***  
1. [tensorflow/models/autoencoder](https://github.com/BaeSeulki/models/tree/master/autoencoder)
2. [珠算：贝叶斯深度学习的GPU库](https://github.com/thu-ml/zhusuan)  

	> 来自机器之心的[简介](https://www.jiqizhixin.com/articles/2017-05-09-4)
	
### ***Extend***
1. SGVB (stochastic gradient variational bayes) 随机梯度变分贝叶斯
2. [CVAE 条件变分自编码器](https://zhuanlan.zhihu.com/p/25518643)

# 参数初始化方法
##  Xavier Initialization
### ***About***
> 它的特点是会根据某一层网络的输入输出节点数量自动调整最合适的分布。

### ***Related Papers***
[Understanding the difficulty of training deep feedforward neural networks](http://machinelearning.wustl.edu/mlpapers/paper_files/AISTATS2010_GlorotB10.pdf).Xavier & Yoshua 2010.   
### ***Related Blogs***
1. 简书—[自编码器参数初始化方法-Xavier initialization](http://www.jianshu.com/p/4e53d3c604f6)
2. 知乎 — [深度前馈网络与Xavier初始化原理](https://zhuanlan.zhihu.com/p/27919794) 

## Layer-sequential unit-variance (LSUV) initialization
### ***Related Papers***
[All you need is a good init](https://arxiv.org/pdf/1511.06422.pdf)

## Recent methods
* [All You Need is Beyond a Good Init: Exploring Better Solution for Training
Extremely Deep Convolutional Neural Networks with Orthonormality and
Modulation](https://arxiv.org/pdf/1703.01827.pdf) ；可进一步参考其 Related Work。

  

