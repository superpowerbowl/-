# 神经网络模型训练及测试说明

## 1. 模型构建

首先运行 `NeuralNetwork` 类模块代码,完成模型构建。调用该类时需要输入以下参数:

- `input_size`: 输入层维度
- `hidden_size_1`: 第一层隐藏层维度
- `hidden_size_2`: 第二层隐藏层维度 
- `output_size`: 输出层维度 (对于 MNIST 数据集默认为 10)
- `lambda_reg`: L2 正则化系数
- `activation`: 激活函数 (提供了 sigmoid、ReLU 和 tanh 三种选择)

## 2. 训练

训练部分实现了交叉熵损失和 L2 正则化损失的计算,并使用小批量 SGD 优化器进行训练。每个批次包含 600 个数据,每轮训练学习率下降为原本的 97%。

本实验将训练轮数设置为 25 轮。每轮训练结果中,根据验证集上的准确度得分保存最优模型参数。最终输出最优权重参数和最优准确率得分,并可视化每轮训练的测试集和验证集上的损失、验证集上的准确率。

## 3. 参数查找

`grid_search` 函数针对学习率、L2 正则化系数以及隐藏层大小进行网格搜索,以获得最优超参数组合。并可视化神经网络的最优参数。

调用该函数即可进行包含参数查找的模型训练。

## 4. 测试

调用已训练好的最优权重参数直接输入给神经网络模型,前向传播输出结果计算准确率,即为测试集上的测试效果。直接运行该模块即可。
