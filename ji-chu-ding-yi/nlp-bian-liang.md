# NLP变量

**一、NLP变量定义**

&#x20;   NLP变量是指从病案非结构化文本中提取出关键信息并进行数据解析、归一、聚合后的变量代称。例如病理类型、肿瘤原发部位和原发肿瘤大小等。基于不同的维度，NLP变量可分为病案NLP变量和主索引NLP变量。

**二、NLP变量特点**

&#x20;   NLP变量具有标准化、唯一性、原子性、多源性等特点。

* 标准化：NLP变量包括原值和标准化值，例如RMS术前TNM分期的原值是1期，标准化值是I。
* 唯一性：标准化值是唯一的，例如RMS术前TNM分期的标准化值不能既是II又是III。
* 原子性：变量定义不可再拆分，例如肿瘤大小可再分为原发肿瘤大小、转移肿瘤大小，因此肿瘤大小不可作为NLP变量。
* 多源性：变量值可能来自于多个来源，例如原发肿瘤大小这个NLP变量，不同检查方式查出来的原发肿瘤大小可能不一致。

**三、NLP变量清单**

<table><thead><tr><th width="83">序号</th><th width="155">NLP变量英文名称</th><th width="130">NLP变量中文名称</th><th>标准化分类</th><th>分类依据</th><th>文献/指南来源</th></tr></thead><tbody><tr><td>1</td><td>ncDiagnosisAge</td><td>确诊时年龄</td><td>＜1岁，1-9岁，≥10岁</td><td>根据治疗失败风险分类，文献与指南均表明：1岁以下婴儿及10岁以上儿童，与1~9岁儿童相比预后不佳</td><td>Age is an independent prognostic factor in rhabdomyosarcoma: a report from the Soft Tissue Sarcoma Committee of the Children′s Oncology Group；儿童及青少年横纹肌肉瘤CACA指南</td></tr><tr><td>2</td><td>ncPathologicalClassification</td><td>病理类型</td><td>胚胎型、腺泡型、梭形细胞/硬化型、多形型</td><td>WHO骨与软组织肉瘤分类（第五版）</td><td>WHO Classification of Tumours • 5th Edition Soft Tissue and Bone Tumours</td></tr><tr><td>3</td><td>ncPrimarySite</td><td>肿瘤原发部位</td><td>眼眶、脑膜旁头颈部、非脑膜旁头颈部、膀胱/前列腺泌尿生殖道、非膀胱/前列腺泌尿生殖道、四肢、其他部位、未知</td><td>肿瘤好发部位和TNM-UICC分期中的原发部位</td><td>Adolescents and young adults with rhabdomyosarcoma treated in the European paediatric Soft tissue sarcoma Study Group (EpSSG) protocols: a cohort study</td></tr><tr><td>4</td><td>ncPrimaryTumorSize</td><td>原发肿瘤大小</td><td>≤5cm ,＞5cm，未知</td><td>TNM-UICC分期中的肿瘤最大直径</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>5</td><td>ncLevel</td><td>治疗前TNM分期</td><td>I、II、III、IV</td><td>TNM-UICC-分期</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>6</td><td>ncIrs</td><td>IRS术后-病理分期</td><td>I、II、III、IV</td><td>IRSG术后-病理分组</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>7</td><td>ncRiskGroup</td><td>危险度分组</td><td>低危、中危、高危、未知</td><td>COG危险度分组</td><td>中国肿瘤整合诊治指南（CACA指南）-儿童及青少年横纹肌肉瘤</td></tr><tr><td>8</td><td>ncTnmT</td><td>原发肿瘤侵袭性（T）</td><td>T1：局限于原发器官或组织、T2：延伸至原发组织或器官之外、Tx：有关原发肿瘤的信息不足</td><td>TNM-UICC-分期</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>9</td><td>ncTnmN</td><td>淋巴结受累情况（N）</td><td>N0：无淋巴结受累证据、N1：区域淋巴结受累的证据、Nx：无淋巴结受累信息</td><td>TNM-UICC-分期</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>10</td><td>ncTnmM</td><td>远处转移（M）</td><td>M0：无远处转移、M1：远处转移</td><td>TNM-UICC-分期</td><td>An update on rhabdomyosarcoma risk stratification and the rationale for current and future Children’s Oncology Group clinical trials</td></tr><tr><td>11</td><td>ncFoxo1</td><td>FOXO1融合状态</td><td>阴性、阳性、未知</td><td>是否存在FOXO1基因染色体易位</td><td></td></tr><tr><td>12</td><td> ncTnm</td><td>TNM</td><td>TxNxMx</td><td></td><td></td></tr></tbody></table>

**四、NLP变量示例**

<figure><img src="../.gitbook/assets/image (24).png" alt=""><figcaption><p>NLP变量-IRS术后-病理分期</p></figcaption></figure>

**五、NLP变量新增流程**

<div align="center">

<figure><img src="../.gitbook/assets/image (17).png" alt="" width="364"><figcaption></figcaption></figure>

</div>
