# Ungrammatical-Sentence

Collecting some writing error make by naive speecher.


## Data format
Data format is json:
```json
{
    "text": "一个种单的基于动作价值的（Action-Value Based）方法是，通过将在时间 t 前选择动作 a 所获得的总体奖励除以这个动作被选择的次数来估算 Qt(a) 的值。",
    "errors": [
        {
            "position": [
                2,
                4
            ],
            "correction": "简单",
            "type": "输入法",
            "difficulty": 1
        }
    ],
    "source": {
        "name": "深度强化学习(中文版)-p48",
        "type": "book",
        "url": "https://deepreinforcementlearningbook.org/assets/pdfs/深度强化学习(中文版-彩色压缩).pdf"
    },
    "language": "中文"
}
```

## Data Field

+ `text`: A string field that contains the text data.
+ `errors`: An array field that contains errors in text.
  + `position`: An array field that represents the position of the error.
  + `correction`: A string field that represents the correction for the error.
  + `type`: A string field that represents the type of the error.
  + `d-difficulty`: An integer field that represents the difficulty level of detect the error. [1-5]
  + `c-difficulty`: An integer field that represents the difficulty level of correct the error. [1-5]
  + `confusing`: An bool field that represents wether it will make the sentence unclear.
+ `source`: An object field that contains information about the source of the text data.
  + `name`: A string field that represents the name of the source.
  + `type`: A string field that represents the type of the source.
  + `genre`: A string field that represents the genre of the source. (体裁)
  + `topic`: A string field that represents the topic of the source. (主题)
  + `url`: A string field that represents the URL of the source.
+ `language`: A string field that represents the language of the text data.

## Guidelines

### Type
1. `笔误`: 同音字\五笔输入\OCR导致的替换 (1)
1. `语序不当`
    1. `语序不当-定中`: "**巴金的晚年**写了许多优秀的作品。" (2-4)
    1. `语序不当-定状`: "**飞快的18次列车**向北京奔驰。" (2-5)
    1. `语序不当-状补`: "李汉阳**活龙活现讲岳飞**。" (2-5)
    1. `语序不当-壮语修饰` (1-5)
    1. `语序不当-多层定语` "其他学校领导。" (1-5)
    1. `语序不当-多层状语` "把国民经济用先进的科学技术搞上去。" (4-5)
    1. `语序不当-关联词` (4-5)
1. `成分多余`
    1. `成分多余-主语` (2-5)
    1. `成分多余-谓语`: "习惯势力使他对罢黜百家**感到**习以为常。" (2-5)
    1. `成分多余-宾语`: "本书有广大读者**群**。" (2-5)
    1. `成分多余-定语`: (2-5)
    1. `成分多余-定语中心语`: "我们翻开科学史**的记录**。" (2-5)
    1. `成分多余-补语`: "这里不时发生**出**一下使人不安的怪事**来**。" (2-5)
    1. `成分多余-关联词` (2-5)
1. `成分残缺`
    1. `成分残缺-主语`
        1. 滥用介词和 “介词……方位词” 导致主语残缺。 (3-4)
        1. 暗中更换主语导致的残缺。 (4-5)
    1. `成分残缺-谓语`: 生活中十分常见，但特别难以发现和标注。 (3-5)
        1. 一句话说了主语，还没说完谓语，却又另外起了一个头。 (5)
        1. 缺少谓语中心造成的谓语残缺。 (3-5)
    1. `成分残缺-宾语` (3-5)
    1. `成分残缺-定状补` (2-5)
    1. `成分残缺-关联词` (2-5)
1. `句式杂糅` (读起来会感觉不通顺)
    1. `说法混杂`
    1. `前后牵连`: 我们大家有一种愉快的感觉是难以形容的。
1. `搭配不当`
    1. `搭配不当-主谓`: "我市赴北京参观的**代表**由先进生成者***组成***。" (4)
    1. `搭配不当-动宾`: "小米***含*****蛋白质、铁及维生素 B1、 B2 丰富**。" (3)
    1. `搭配不当-定状补`: "***沉思***了**少许**。" (4)
    1. `搭配不当-联合`: "晚会上演出了音乐、舞蹈、**体操**、**武术**等**文艺**节目。" (5)
    1. `搭配不当-关联词`:  (5)

#### TODO
句群语病。

### Difficulty of Detection
1. 绝对错了
1. 
1. 严格来说错了
1.
1. 不确定是否错，但读起来不通顺

### Difficulty of Correction
1. 好改
1.
1. 一般好改
1.
1. 不好改

## Source meta
### Type
+ `书籍` (Book)
+ `网页` (Web)
  + `网页-微博`
  + `网页-小红书`
  + `网页-知乎`
+ `字幕` (Subtitle)

### Genre
+ `专业写作` (Papers)
+ `新闻` (New)
+ `博客`
+ `微博`
+ `小说`
+ `评论`

### Topic
+ `计算机`
