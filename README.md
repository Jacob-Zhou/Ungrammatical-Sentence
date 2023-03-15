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
  + `type`: A string field that represents the type of the error. ["输入法"]
  + `difficulty`: An integer field that represents the difficulty level of the error. [1-9]
+ `source`: An object field that contains information about the source of the text data.
  + `name`: A string field that represents the name of the source.
  + `type`: A string field that represents the type of the source.
  + `genre`: A string field that represents the genre of the source. (体裁)
  + `topic`: A string field that represents the topic of the source. (主题)
  + `url`: A string field that represents the URL of the source.
+ `language`: A string field that represents the language of the text data.

## Guidelines

### Difficulty
1. The easiest for example mis-type by typer
1. 
1. 
1. 
1. 
1. 
1. 
1. 
1. 

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
