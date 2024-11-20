# 实体

**一、实体定义**

&#x20;   实体指的是文本中具有明确指代意义的<mark style="color:red;">词汇或短语</mark>。

**二、实体示例**

<div align="center">

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption><p>数据标注-大报卡</p></figcaption></figure>

</div>

<div align="center">

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption><p>疾病名称实体</p></figcaption></figure>

</div>

**三、实体属性**

（1）类型（Type）

&#x20;   实体的类别，如分期程度、疾病症状等。

（2）状态（Status）

&#x20;   术前/术后状态：术前、术后、不确定

&#x20;   肿瘤是否原发状态：是、否

&#x20;   发生状态：是、否

（3）时间戳（Timestamp）

&#x20;   实体相关事件或信息的时间点，如CT检查的时间

（4）上下文（Context）

&#x20;   实体出现的上下文环境，有助于理解实体的具体含义

（5）关系（Relation）

&#x20;   实体与其他实体之间的联系，例如“苹果公司”与“蒂姆·库克”（CEO）之间的关系

**四、实体来源**

&#x20;   实体识别的过程来源于<mark style="color:red;">模型识别</mark>和<mark style="color:red;">人工标注</mark>。模型识别指使用机器学习或深度学习模型来自动识别文本中的实体， 人工标注指人类专家阅读文本并手动标记出其中的实体。
