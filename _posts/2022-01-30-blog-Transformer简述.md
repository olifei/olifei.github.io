# Transformer和Sequence-to-Sequence简介
Transformer模型结构在NLP领域中大显神通，已经被证明可以高效地处理多种自然语言任务。这里我们主要介绍Transformer模型的结构和细节。

# Sequence-to-Sequence模型和Attention机制
"Attention is all you need"文章提出了Transformer模型和Sequence-to-Sequence结构。Sequence-to-Sequence（Seq2Seq）是一个对序列输入进行转化的神经网络。比如可以将句子的单词序列转化为另一个序列。

Seq2Seq模型在翻译任务上表现良好，经常配合LSTM模型。LSTM模型在处理序列数据时会有选择地记住一些“重要的”信息同时遗忘一些“无关紧要的”信息。一句话就是一种典型的序列数据，LSTM模型天然适合处理这种类型的数据。

Seq2Seq模型包含了一个编码器（encoder）和一个解码器（decoder）。编码器将序列输入数据映射到一个高维空间（n-维向量）。这个高维向量被解码器处理变为模型的输出。输出的序列可以是另一种语言、
符号或者是输入的副本等。

可以将编码器和解码器想象成会说两种语言的人类翻译。翻译具有不同的母语，比如说中文和英文，他们的会的外语是相同的，比如都会法语。将中文翻译成英文的时候，编码器将中文转化成法语。由于解码器也懂法语，所以可以将其转化为英语。这样配合编码器和解码器，我们就可以将中文翻译成英语。

假设在训练刚开始时，编码器和解码器对中间语言的掌握能力都很差。我们需要通过大量的数据让他们进行学习。LSTM模型是对编码器和解码器建模的最基础的结构。那么什么时候才会用到Transformer结构呢？

我们