# 时序理解评测数据集（v1）
本数据集基于MSR-VTT数据集的测试集生成。

# 格式
数据集为jsonl格式，其中每一行的json包括如下信息：
- caption：正例/负例文本
- clip_name：视频文件名
- retrieval_key：编号
对于同一段视频所对应的多个文本中，编号最小者为正例，其余为负例

# 构建方法
1. 提取原文本中的动词
a person is **connecting something to system**

2. 构造模板作为文本生成模型OPT-2.7B的输入
The reverse action of “connecting something to system” is …

3. 对预测结果人工筛选得到负例文本 
a person is disconnecting something from system


# 统计数据
| 负例数量 |  1  |  2  |  3  |  4  |  5  |  总计  |
|  ----   | ---- | ---- | ---- | ---- | ---- | ---- |
| 视频数量 | 143 |  55  |  11  |  2  |  5  | 216 |