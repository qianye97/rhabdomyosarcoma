# 专病库建设流程

**一、总流程图**

<figure><img src="../../.gitbook/assets/image (28).png" alt=""><figcaption><p>专病库建设流程图</p></figcaption></figure>

**二、详细流程**

1. **数据抽取及脱敏**

&#x20;   数据抽取是指通过<mark style="color:red;">创建数据标注任务</mark>将数据从全量库和主题库抽取到原始库和脱敏库。<mark style="color:red;">原始库</mark>中的数据为原始数据，数据前台无法展示、导出和使用，仅用于备份和重新脱敏。<mark style="color:red;">脱敏库</mark>中的数据为脱敏后的数据，数据前台可展示和使用，脱敏信息包括姓名、身份证号、机构名称、地址和电话号码。

2. **自然语言处理**

&#x20;   自然语言处理包括数据标注、模型训练和模型应用。目的是从病案的非结构化文本中提取关键信息，如疾病名称、病理分型、肿瘤分期等，并将这些信息标准化处理，为医疗决策和科研提供支持。

* <mark style="color:red;">数据标注</mark>是指人类专家阅读病案文本并手动标记出其中的实体和实体关系
* <mark style="color:red;">模型训练</mark>是指使用标注好的数据来训练机器学习或深度学习模型的过程，这个阶段的目标是让模型学习如何识别和处理语言数据中的模式和结构
* <mark style="color:red;">模型应用</mark>是指将训练好的模型部署到实际应用中

3. **数据标准化**

&#x20;   数据标准化包括数据归一、数据聚合和人工审核。

* <mark style="color:red;">数据解析和归一</mark>是指在实体映射成病案NLP变量后，对实体的值进行归一化处理
* <mark style="color:red;">数据聚合</mark>是指将以病案为维度的标准变量转换成以主索引为维度的NLP变量
* <mark style="color:red;">人工审核</mark>是指人工对机器处理后的结果进行最终的检查和确认，以确保结果的准确性和可靠性