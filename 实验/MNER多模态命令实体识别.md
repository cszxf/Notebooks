MNER 多模态命名实体识别

# 数据集

- [Twitter2015](https://github.com/jefferyYu/UMT)



- [Twitter2017](https://github.com/jefferyYu/UMT)

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648193541924_2561.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)

# Baseline

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648193331387_8790.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648269588496_7064.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)

实验结果

|                            | twitter2015 | twitter2017 |
| -------------------------- | ----------- | ----------- |
| Bert+CRF                   | 71.81       | 83.44       |
| BasicModel                 | 71.442      | 84.002      |
| MMNerModel（bert+crf+ViT） | 72.013      | 84.303      |
| UMT                        | 73.41       | 85.31       |
| UMGF                       | **74.85**   | **85.51**   |



# 参考资料

[BIOS标注](https://zhuanlan.zhihu.com/p/147537898)

[多模态NER相关论文](https://zhuanlan.zhihu.com/p/161385278)

[多模态深度学习综述：网络结构设计和模态融合方法汇总](https://blog.csdn.net/tMb8Z9Vdm66wH68VX1/article/details/112386111)

[实体关系的联合抽取总结](https://zhuanlan.zhihu.com/p/74886839)

# 2020

## Improving Multimodal Named Entity Recognition via Entity Span Detection with Unified Multimodal Transformer 

[引用](https://blog.csdn.net/qq_43703681/article/details/113748435)

### 现有方法问题

1. 没有考虑一词多义的上下文表示。
2. 虽然当前方法基于多模态建模获得基于文本的视觉表示，但是在最后隐藏层依然还是只基于文本的表示来进行预测，没有将视觉信息融合进去。
3. 视觉偏差：通常图片只涉及文本中的某一个两个实体，并不涉及其他实体，如果一味的将视觉信息融合进所有实体的识别当中，会导致相关实体识别准确率很高，但是其他实体识别率降低。

### 模型

首先通过Bert和ResNet分别得到文本和图片的上下文向量和视觉特征，之后通过MMI（Transformer的跨模态版本）产生关于文本的视觉表征和关于图片的文本表征。最后通过辅助边界检测任务消除视觉偏差问题。

#### 贡献

- 对于MNER任务首次提出了多模态的Transformer。
- 基于多模态Transformer，设计了一个MNER联合框架，为消除视觉偏差而引入了实体跨度检测辅助任务。

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648369466109_7383.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)

### 实验结果

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648193331387_8790.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)



# 2021

## **Multi-modal Graph Fusion for Named Entity Recognition with Targeted Visual Guidance**

[引用](https://zhuanlan.zhihu.com/p/349064943)

### 模型

![](https://dev.azure.com/conansteve/87be1d78-05d4-41bd-87b2-a023d463dcd2/_apis/git/repositories/075c6005-9f0d-4b8c-97a7-60d87486d3f4/items?path=%2F1648369522234_6085.png&versionDescriptor%5BversionOptions%5D=0&versionDescriptor%5BversionType%5D=0&versionDescriptor%5Bversion%5D=master&resolveLfs=true&%24format=octetStream&api-version=5.0)



### 评价

只是建模用了图，实际没有用GNN来来训练

# Think





| 能否引入外部知识库，比如Freebase Dictionary，来解决关联图像噪声 | ![img](https://ah0aangfha.feishu.cn/space/api/box/stream/download/asynccode/?code=MmE0YTMyYzAyNDk1ZDgyYjBjY2E0ODM0ODY0NmYxM2NfbmFUdkltQU5qT29HQ1RhSjBiaTRGMzNCcE5peFVOb2xfVG9rZW46Ym94Y250VVB5U2xOTHVnS0VkVlp4Z0hJcWxkXzE2NDgxOTMwNTM6MTY0ODE5NjY1M19WNA) |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| 对于无图像的推文不输入默认图像，而是0向量，借鉴short cut思想，直接在融合模块不进行模态间融合，在预测层，直接将默认第一层输入，使预测结果尽量贴合BERT-CRF模型 | ![img](https://ah0aangfha.feishu.cn/space/api/box/stream/download/asynccode/?code=NTMxYjk0ODU0MDNkNWYxMzdlYzlmMGRmYTUyYmM0YjNfZnVmdHNJR1UyM1BkeDExMmhmWUFsVVlDc3AwQmZRaFdfVG9rZW46Ym94Y25ycjdWd3RHN3VQVlBLVUxKRkg2UXZoXzE2NDgxOTMwNTM6MTY0ODE5NjY1M19WNA) |

- 如何降低抽象图像或者卡通图像等图像噪声？
- 加个单独的分类器判断图像是否是卡通图和表情包，如果是，就降低图像的对文本的权重。
- 适当增加图像相关联的词语获得的注意力权重。
- 兼容BERT-CRF的UMT





![img](https://ah0aangfha.feishu.cn/space/api/box/stream/download/asynccode/?code=ODBlZGU5ZWRhY2ZjOTMwMjFiYjI2NTEwZjU3YWUyOWRfZllUTnZmQlFLMFc1Z1d4U3pJWU81NFdzd3NWV2RSTFpfVG9rZW46Ym94Y25zT3NQQmZoa0hiV2NyeXlNNTZ1SVRiXzE2NDgxOTMwNTM6MTY0ODE5NjY1M19WNA)