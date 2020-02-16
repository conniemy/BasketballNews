# BasketballNews
## 篮球新闻自动写作数据集
### 文件构成
本数据集是篮球新闻自动写作相关文字直播数据库及篮球知识图谱库，包含三个子目录：
* `Neo4jData`目录为篮球相关的知识图谱，以Neo4j知识图谱库的形式存储；
* `knowledgeGraph`目录为实现新闻自动生成时调用的知识图谱数据，以Python语言可调用的方式存储；
* `textlive`目录下是用于新闻自动写作时每场篮球比赛对应初始文字直播数据。

### Neo4jData
本目录下为windows下的篮球相关知识图谱Neo4j工程文件，具体图谱数据储存在该文件夹里的import文件夹下。

#### 图谱数据
本知识图谱数据为2018-2019赛季NBA各球队的球员名单、各球队信息、球队之间的胜负关系等，大部分数据为txt格式或文件格式，少数为csv格式。
在构建的篮球赛事知识图谱中，定义了3个概念类，4种关系和27个属性，具体如下表所示： 

概念类|属性名称|属性说明
-|-|-
|
`  `|中文名|球员的中文名称
`  `|英文名|球员的英文名
`  `|身高|球员的身高
`  `|体重|球员的体重
球员|号码|球员的球衣号码
`  `|位置|球场上打的位置
`  `|年龄|现在的年龄
`  `|外号|球员的外号
`  `|学校|球员毕业的学校
`  `|荣誉|曾获得的荣誉
|
`  `|名称|球队的中文名称
`  `|英文别称|球队的英文名称
球队|别名|球队的别名
`  `|半区|球队所在的半区
`  `|分区|球队所在的具体分区
`  `|建队时间|球队创立时间
|
`  `|时间|比赛的时间
`  `|地点|比赛的地点
`  `|最终比分|比赛结束时的比分
`  `|主队第一节得分|主队在第二节最后得分
`  `|主队第二节得分|主队在第二节最后得分
比赛|主队第三节得分|主队在第三节最后得分
`  `|主队第四节得分|主队在第四节最后得分
`  `|客队第一节得分|客队在第一节最后得分
`  `|客队第二节得分|客队在第二节最后得分
`  `|客队第三节得分|客队在第三节最后得分
`  `|客队第四节得分|客队在第四节最后得分
|

根据上表建立篮球知识图谱，得到篮球赛事知识图谱中节点的总数目有5893个，其中现役球员节点数量有620个，退役球员节点3407个，球队节点数量有30个，抽取的比赛场数由1985年起到2019年一共有43510场，但是需要用到的比赛节点数量为1836。

统计数据|数值
-|-
实体类数量|3
关系数量|4
属性数量|27
球员节点数量|4027
现役球员节点数量|620
退役球员节点数量|3407
球队数量|30
比赛场次|43510
比赛节点数量|1836
总结点数量|5893

### knowledgeGraph
存储着知识图谱数据，根据上述Neo4jData中建立的篮球知识图谱，为实现新闻自动生成时调用的知识图谱数据，以Python语言可调用的方式存储。

### textlive 
储存着由爬虫从新浪网等网站爬取的2018-2019赛季NBA图文直播数据，以及CBA 2018-2019赛季数据，共有1280场文字直播数据。

#### 运行环境
Python3.7+py2neo+BeautifulSoup
