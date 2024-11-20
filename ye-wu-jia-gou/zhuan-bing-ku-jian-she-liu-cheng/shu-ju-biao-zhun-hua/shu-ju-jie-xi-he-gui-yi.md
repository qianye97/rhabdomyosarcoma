# 数据解析和归一

**一、数据解析**

&#x20;   数据解析又分为实体的解析和实体关系的解析，即将实体和实体关系映射成以病案为维度的NLP变量。

（1）实体映射表

<table><thead><tr><th width="140">实体类型</th><th width="135">实体状态名称</th><th width="66">值</th><th width="130">对应NLP变量中文名</th><th width="248">对应NLP变量英文名</th></tr></thead><tbody><tr><td>FOXO1状态</td><td>阴性/阳性</td><td>阳性</td><td>FOXO1状态</td><td>ncFoxo1</td></tr><tr><td>分期程度</td><td>术前/术后</td><td>术前</td><td>术前分期</td><td>ncLevel</td></tr><tr><td>分期程度</td><td>术前/术后</td><td>术后</td><td>术后分组</td><td>ncIrs</td></tr><tr><td>病理类型</td><td></td><td></td><td>病理类型</td><td>ncPathologicalClassification</td></tr><tr><td>TNM</td><td></td><td></td><td>TNM</td><td>ncTnm</td></tr><tr><td>危险度分组</td><td></td><td></td><td>危险度分组</td><td>ncRiskGroup</td></tr><tr><td>肿瘤大小</td><td>是否原发</td><td>是</td><td>原发肿瘤大小</td><td>ncPrimaryTumorSize</td></tr><tr><td>疾病症状</td><td>发生状态</td><td>有</td><td>疾病症状</td><td>ncSymptom</td></tr></tbody></table>

（2）实体关系映射表 &#x20;

<table><thead><tr><th width="85">实体关系</th><th width="142">实体1类型</th><th width="162">实体2类型</th><th width="137">对应病案NLP变量中文名</th><th width="156">对应病案NLP变量英文名</th><th width="149">对应病案NLP变量取值</th></tr></thead><tbody><tr><td>肿瘤危险度分组</td><td>疾病名称</td><td>危险度分组</td><td>危险度分组</td><td>ncRiskGroup</td><td>危险度分组</td></tr><tr><td>肿瘤原发部位</td><td>临床发现</td><td>解剖部位</td><td>肿瘤原发部位</td><td>ncPrimarySite</td><td>解剖部位</td></tr><tr><td>肿瘤病理类型</td><td>疾病名称</td><td>病理类型</td><td>病理类型</td><td>ncPathologicalClassification</td><td>病理类型</td></tr><tr><td>肿瘤侵袭性</td><td>临床发现</td><td>临床事件</td><td>原发肿瘤侵袭性（T）</td><td>ncTnmT</td><td>临床发现+临床事件</td></tr><tr><td>淋巴结受累情况</td><td>组织细胞</td><td>临床事件</td><td>淋巴结受累情况（N）</td><td>ncTnmN</td><td>组织细胞+临床事件</td></tr><tr><td>远处转移</td><td>临床发现/解剖部位</td><td>临床事件</td><td>远处转移（M）</td><td>ncTnmM</td><td>临床发现/解剖部位+临床事件</td></tr><tr><td>新发时间</td><td>疾病名称</td><td>时间</td><td>新发时间</td><td>ncNewOccurTime</td><td>时间</td></tr></tbody></table>

**二、数据归一**

&#x20;   数据归一是指对实体的值进行归一化处理，即将原值转换为<mark style="color:red;">标准化值</mark>。不同的实体类型，归一化策略也不同，策略如下：

（1）FOXO1状态

&#x20;   若实体状态为阳性，则实体的标准化值为阳性。

&#x20;   若实体状态为阴性，则实体的标准化值为阴性。

（2）肿瘤大小

&#x20;   将肿瘤大小的值转换为肿瘤最大直径(cm)，总共分为两步：

&#x20;   第一步，计算肿瘤最大直径，若肿瘤大小的书写形式为x\*y\*z，则肿瘤最大直径为max(x,y,z)，若肿瘤大小的书写形式为x\*y，则肿瘤最大直径为max(x,y)；

&#x20;   第二步，单位转换，若肿瘤大小中的原值出现\[mm,Mm,mM,MM,毫米,立方毫米]，则肿瘤最大直径=肿瘤最大直径/10。

（3）时间

&#x20;   将不同的时间类型转换为标准化格式的时间，标准化时间格式为yyyy、yyyy-mm和yyyy-mm-dd。

（4）分期程度

<table><thead><tr><th width="98">原值</th><th width="119">标准化值</th></tr></thead><tbody><tr><td>1</td><td>Ⅰ</td></tr><tr><td>一</td><td>Ⅰ</td></tr><tr><td>I</td><td>Ⅰ</td></tr><tr><td>Ⅰ</td><td>Ⅰ</td></tr><tr><td>2</td><td>Ⅱ</td></tr><tr><td>二</td><td>Ⅱ</td></tr><tr><td>II</td><td>Ⅱ</td></tr><tr><td>Ⅱ</td><td>Ⅱ</td></tr><tr><td>3</td><td>Ⅲ</td></tr><tr><td>三</td><td>Ⅲ</td></tr><tr><td>III</td><td>Ⅲ</td></tr><tr><td>Ⅲ</td><td>Ⅲ</td></tr><tr><td>4</td><td>Ⅳ</td></tr><tr><td>四</td><td>Ⅳ</td></tr><tr><td>IV</td><td>Ⅳ</td></tr><tr><td>Ⅳ</td><td>Ⅳ</td></tr></tbody></table>

（5）病理类型

<table><thead><tr><th width="208">原值</th><th width="233">标准化值</th></tr></thead><tbody><tr><td>多形型</td><td>多形型</td></tr><tr><td>多形性</td><td>多形型</td></tr><tr><td>梭型细胞</td><td>梭形细胞/硬化型</td></tr><tr><td>梭形细胞</td><td>梭形细胞/硬化型</td></tr><tr><td>硬化型</td><td>梭形细胞/硬化型</td></tr><tr><td>硬化性</td><td>梭形细胞/硬化型</td></tr><tr><td>硬化型/梭形细胞型</td><td>梭形细胞/硬化型</td></tr><tr><td>腺泡样</td><td>腺泡型</td></tr><tr><td>胚胎型</td><td>胚胎型</td></tr><tr><td>胚胎性</td><td>胚胎型</td></tr><tr><td>胎儿性</td><td>胚胎型</td></tr><tr><td>腺泡型</td><td>腺泡型</td></tr><tr><td>腺泡状</td><td>腺泡型</td></tr><tr><td>腺泡性</td><td>腺泡型</td></tr><tr><td>胚胎性-腺泡状混合型</td><td>胚胎性-腺泡状混合型</td></tr><tr><td>腺泡胚胎混合型</td><td>胚胎性-腺泡状混合型</td></tr></tbody></table>

（6）危险度分组

<table><thead><tr><th width="152">原值</th><th width="137">标准化值</th></tr></thead><tbody><tr><td>中-高危</td><td>中-高危</td></tr><tr><td>中危</td><td>中危</td></tr><tr><td>中危组</td><td>中危</td></tr><tr><td>中枢侵犯组</td><td>中枢侵犯组</td></tr><tr><td>低危</td><td>低危</td></tr><tr><td>低危组</td><td>低危</td></tr><tr><td>标危组</td><td>标危组</td></tr><tr><td>超高危组</td><td>超高危组</td></tr><tr><td>高危</td><td>高危</td></tr><tr><td>高危组</td><td>高危</td></tr></tbody></table>

（7）疾病名称

<table><thead><tr><th width="139">原值</th><th width="120">标准化值</th></tr></thead><tbody><tr><td>横纹肌瘤</td><td>横纹肌肉瘤</td></tr><tr><td>横纹肌肉</td><td>横纹肌肉瘤</td></tr><tr><td>横纹肌肉瘤</td><td>横纹肌肉瘤</td></tr></tbody></table>

（8）解剖部位

<table><thead><tr><th width="144">原值</th><th width="248">标准化值</th></tr></thead><tbody><tr><td>会阴</td><td>会阴-肛周区</td></tr><tr><td>会阴部</td><td>会阴-肛周区</td></tr><tr><td>前列腺</td><td>膀胱/前列腺泌尿生殖道</td></tr><tr><td>右上肢</td><td>四肢</td></tr><tr><td>右侧扁桃体</td><td>非脑膜旁头颈部</td></tr><tr><td>右侧眼眶</td><td>眼眶</td></tr><tr><td>右侧睾丸</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>右侧胸腔</td><td>胸腔内</td></tr><tr><td>右侧腋下</td><td>其他</td></tr><tr><td>右侧腰部</td><td>躯干</td></tr><tr><td>右侧腹股沟</td><td>其他</td></tr><tr><td>右侧臀部</td><td>其他</td></tr><tr><td>右侧阴囊壁</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>右侧鞍旁</td><td>脑膜旁头颈部</td></tr><tr><td>右侧颌面部</td><td>非脑膜旁头颈部</td></tr><tr><td>右侧骶尾部</td><td>躯干</td></tr><tr><td>右侧鼻窦</td><td>脑膜旁头颈部</td></tr><tr><td>右侧鼻翼</td><td>非脑膜旁头颈部</td></tr><tr><td>右侧鼻腔</td><td>脑膜旁头颈部</td></tr><tr><td>右前臂</td><td>四肢</td></tr><tr><td>右手</td><td>四肢</td></tr><tr><td>右手背</td><td>四肢</td></tr><tr><td>右手臂</td><td>四肢</td></tr><tr><td>右眶颅沟通</td><td>脑膜旁头颈部</td></tr><tr><td>右眼眶</td><td>眼眶</td></tr><tr><td>右腋下</td><td>其他</td></tr><tr><td>右腮腺</td><td>非脑膜旁头颈部</td></tr><tr><td>右腰背部</td><td>躯干</td></tr><tr><td>右腰部</td><td>躯干</td></tr><tr><td>右臀部</td><td>其他</td></tr><tr><td>右足外侧</td><td>四肢</td></tr><tr><td>右足底</td><td>四肢</td></tr><tr><td>右颞部</td><td>非脑膜旁头颈部</td></tr><tr><td>右鼻咽</td><td>脑膜旁头颈部</td></tr><tr><td>右鼻旁</td><td>非脑膜旁头颈部</td></tr><tr><td>右鼻翼</td><td>非脑膜旁头颈部</td></tr><tr><td>右鼻腔</td><td>脑膜旁头颈部</td></tr><tr><td>右鼻鼻前庭</td><td>非脑膜旁头颈部</td></tr><tr><td>咽部</td><td>非脑膜旁头颈部</td></tr><tr><td>外阴</td><td>会阴-肛周区</td></tr><tr><td>子宫颈</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>左下肢</td><td>四肢</td></tr><tr><td>左下颌</td><td>非脑膜旁头颈部</td></tr><tr><td>左侧大腿根部</td><td>四肢</td></tr><tr><td>左侧小腿</td><td>四肢</td></tr><tr><td>左侧睾丸</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>左侧纵膈</td><td>胸腔内</td></tr><tr><td>左侧胸腔</td><td>胸腔内</td></tr><tr><td>左侧胸膜</td><td>胸腔内</td></tr><tr><td>左侧腘窝</td><td>四肢</td></tr><tr><td>左侧腮腺区域</td><td>非脑膜旁头颈部</td></tr><tr><td>左侧腹膜后</td><td>其他</td></tr><tr><td>左侧足底部</td><td>四肢</td></tr><tr><td>左侧鞘膜</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>左侧颈部</td><td>非脑膜旁头颈部</td></tr><tr><td>左侧鼻腔</td><td>非脑膜旁头颈部</td></tr><tr><td>左前上纵膈</td><td>胸腔内</td></tr><tr><td>左前臂</td><td>四肢</td></tr><tr><td>左外耳道</td><td>非脑膜旁头颈部</td></tr><tr><td>左大腿</td><td>四肢</td></tr><tr><td>左大腿远端</td><td>四肢</td></tr><tr><td>左小腿</td><td>四肢</td></tr><tr><td>左手</td><td>四肢</td></tr><tr><td>左眶</td><td>眼眶</td></tr><tr><td>左眼眶</td><td>眼眶</td></tr><tr><td>左耳后</td><td>非脑膜旁头颈部</td></tr><tr><td>左肩胛骨</td><td>躯干</td></tr><tr><td>左肩部</td><td>四肢</td></tr><tr><td>左肾</td><td>其他</td></tr><tr><td>左胸壁</td><td>躯干</td></tr><tr><td>左腋下</td><td>其他</td></tr><tr><td>左腮</td><td>非脑膜旁头颈部</td></tr><tr><td>左腰部</td><td>躯干</td></tr><tr><td>左腹股沟</td><td>其他</td></tr><tr><td>左臀部</td><td>其他</td></tr><tr><td>左阴囊</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>左面部</td><td>非脑膜旁头颈部</td></tr><tr><td>左面颊部</td><td>非脑膜旁头颈部</td></tr><tr><td>左颈部</td><td>非脑膜旁头颈部</td></tr><tr><td>左颊部</td><td>非脑膜旁头颈部</td></tr><tr><td>左颌面部</td><td>非脑膜旁头颈部</td></tr><tr><td>左颞部</td><td>非脑膜旁头颈部</td></tr><tr><td>左鼻腔</td><td>非脑膜旁头颈部</td></tr><tr><td>椎管内</td><td>躯干</td></tr><tr><td>盆腔</td><td>其他</td></tr><tr><td>盆腔膀胱</td><td>膀胱/前列腺泌尿生殖道</td></tr><tr><td>眼眶</td><td>眼眶</td></tr><tr><td>精阜旁</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>纵膈</td><td>胸腔内</td></tr><tr><td>纵隔</td><td>胸腔内</td></tr><tr><td>耳后</td><td>非脑膜旁头颈部</td></tr><tr><td>肛门</td><td>会阴-肛周区</td></tr><tr><td>肝左内叶</td><td>肝胆</td></tr><tr><td>肝胆管</td><td>肝胆</td></tr><tr><td>胆道</td><td>肝胆</td></tr><tr><td>背部</td><td>躯干</td></tr><tr><td>胸部</td><td>躯干</td></tr><tr><td>脑膜旁</td><td>脑膜旁头颈部</td></tr><tr><td>脑膜旁区域</td><td>脑膜旁头颈部</td></tr><tr><td>脑膜旁区域（颞下窝）</td><td>脑膜旁头颈部</td></tr><tr><td>腹</td><td>躯干</td></tr><tr><td>腹股沟</td><td>其他</td></tr><tr><td>腹腔</td><td>躯干</td></tr><tr><td>腹膜后</td><td>其他</td></tr><tr><td>腹部</td><td>躯干</td></tr><tr><td>膀胱</td><td>膀胱/前列腺泌尿生殖道</td></tr><tr><td>膀胱前列腺</td><td>膀胱/前列腺泌尿生殖道</td></tr><tr><td>膀胱左侧壁</td><td>膀胱/前列腺泌尿生殖道</td></tr><tr><td>臀部</td><td>其他</td></tr><tr><td>舌部</td><td>非脑膜旁头颈部</td></tr><tr><td>阴囊</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>阴道</td><td>非膀胱/前列腺泌尿生殖道</td></tr><tr><td>面部</td><td>非脑膜旁头颈部</td></tr><tr><td>鞍区</td><td>脑膜旁头颈部</td></tr><tr><td>颅底</td><td>脑膜旁头颈部</td></tr><tr><td>颌面部</td><td>非脑膜旁头颈部</td></tr><tr><td>骶尾部</td><td>躯干</td></tr><tr><td>鼻咽</td><td>脑膜旁头颈部</td></tr><tr><td>鼻咽部</td><td>脑膜旁头颈部</td></tr><tr><td>鼻炎部</td><td>脑膜旁头颈部</td></tr><tr><td>鼻翼</td><td>非脑膜旁头颈部</td></tr><tr><td>鼻腔内</td><td>脑膜旁头颈部</td></tr></tbody></table>
