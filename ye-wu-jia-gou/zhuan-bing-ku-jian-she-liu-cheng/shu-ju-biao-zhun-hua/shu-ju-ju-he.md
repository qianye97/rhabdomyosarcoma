# 主索引归档

**一、定义**

&#x20;   主索引归档是指将以病案为维度的NLP变量转换成以主索引为维度的NLP变量。

**二、主索引归档规则**

<table><thead><tr><th width="81">序号</th><th width="244">NLP变量英文名称</th><th width="196">NLP变量中文名称</th><th>主索引归档规则</th></tr></thead><tbody><tr><td>1</td><td>ncDiagnosisAge</td><td>确诊时年龄</td><td>发生时间最早</td></tr><tr><td>2</td><td>ncPathologicalClassification</td><td>病理类型</td><td>发生时间最早，主诉>现病史>其他</td></tr><tr><td>3</td><td>ncPrimarySite</td><td>肿瘤原发部位</td><td>发生时间最早</td></tr><tr><td>4</td><td>ncPrimaryTumorSize</td><td>原发肿瘤大小</td><td>根据实体瘤新反应评估标准：修订版 RECIST 指南（1.1 版）优先选择CT（CT 是目前最好的、可重复的测量病变的方法，可用于选定的反应评估）</td></tr><tr><td>5</td><td>ncLevel</td><td>治疗前TNM分期</td><td>发生时间最早</td></tr><tr><td>6</td><td>ncIrs</td><td>IRS术后-病理分期</td><td>发生时间最早</td></tr><tr><td>7</td><td>ncRiskGroup</td><td>危险度分组</td><td>发生时间最早</td></tr><tr><td>8</td><td>ncTnmT</td><td>原发肿瘤侵袭性（T）</td><td>发生时间最早</td></tr><tr><td>9</td><td>ncTnmN</td><td>淋巴结受累情况（N）</td><td>发生时间最早</td></tr><tr><td>10</td><td>ncTnmM</td><td>远处转移（M）</td><td>发生时间最早</td></tr><tr><td>11</td><td>ncFoxo1</td><td>FOXO1融合状态</td><td>发生时间最早</td></tr></tbody></table>

