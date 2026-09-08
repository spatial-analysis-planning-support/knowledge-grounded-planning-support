# 02 Annotated Samples | 标注样本与数据格式

Annotated samples in ms-swift training data format (JSON), each paired with a street-view image under `images/`. The five samples cover the five diagnosis rating levels of the safety dimension, illustrating the data format used for training and inference.

标注样本为 ms-swift 训练数据格式（JSON），每个样本与 `images/` 下的街景图像一一对应。五个样本覆盖安全性层级的五个诊断评级，用于说明训练与推理所用的数据格式。

| File 文件 | Description 说明 |
|:---|:---|
| `image_*.json` | Annotation in ms-swift message format (system prompt + user input + assistant response) ms-swift 消息格式标注（system 提示词 + user 输入 + assistant 应答） |
| `images/image_*.jpg` | Corresponding street-view image 对应街景图像 |
