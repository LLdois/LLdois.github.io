---
title: 手写Transformer
date: 2025-03-16 22:46:32
tags:
---
在看完李沐大神的动手学深度学习系列后，之前很多模糊的不清的概念都清晰了。才意识到最好的学习方式就是实践，一直想抽时间手写一下经典的网络，那就先从Transformer开始吧，原始论文地址：[Attention Is All You Need](https://arxiv.org/abs/1706.03762)。Transformer是一个seq2seq模型，原始论文一共做了两种任务:translation task和English Constituency Parsing。本文使用hugging face的一个繁体中文与英文的数据集（[coct-en-zh-tw-translations-twp-300k](https://huggingface.co/datasets/zetavg/coct-en-zh-tw-translations-twp-300k)），实现一个英文到繁体中文的翻译任务。
# 1、模型总览
本图能很好的概括整个Transformer结构，本节将按照作者的个人理解浅显的分析一下模型的数据流动（以本文要做的翻译任务为例）。
![](https://markdown-tuchuang-lldois.oss-cn-beijing.aliyuncs.com/blog_images20250316175152663.png)
# 2、token化输入数据
# 3、embedding层
当把输入的字符串转化为在vocab中的id后，神经网络已经可以处理了，假设vocab大小为12000，此时
# 4、多头注意力
scale（没有会导致梯度消失，从softmax导数来推），加性注意力，tensor的内存排列,mask注意力(embedding层的padding_idx参数必须为0)
# 5、残差和LayerNorm
推理时的layernorm的均值，方差，layernorm和batchnorm的区别
# 6、FFN
Position-wise，是相对于Depth-wise Convolution而言。nn.linear的用法。