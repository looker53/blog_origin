Title: 如果是的。
Date: 2010-12-03 11:20
Category: Review

## 什么是 xml ？

xml 是一种和 html 非常类似的语言，采取一定的格式展示数据。
```xml
<note>
<to>你</to>
<from>我</from>
<heading>提醒</heading>
<body>今晚八点，不见不散</body>
</note>
```
这个例子非常形象的指明：
- 这是一个便条
- 给你的
- 我写的
- 标题是：提醒
- 内容是：今晚八点，不见不散

## 接口当中为什么会有 xml ?
仔细一点会发现， xml 的作用和 json 实在是太像了。 上一个例子中，可以用 json 来表达：
```json
{
    "note": {
        "to": "你",
        "from": "我",
        "heading": "提醒",
        "body": "今晚八点，不见不散",
    }
}
```

现在，大多数接口都是采用 json 进行数据传递， xml 已经被冷落了，主要的原因是：
- json 数据传输量较小，xml 常常要使用各种属性，冗余信息较多；
- json 支持数字, 布尔， null, 数组，对象等通用格式，xml 都是文本；
- json 解析更方便


但是，还是有一些公司的接口是采用 xml, 比如大名鼎鼎的微信，很多接口还是采用 xml。 原因是 xml 在一些特定领域还占有一些优势：

- 可读性稍微占优势；
- 对于 UI 页面，可以更方便的使用属性这样一种形态进行页面数据的传输，比如安卓应用。
- 历史优势。 xml 相比 json 发展更早，还有很多有经验的程序员偏爱 xml, Java 程序员有喜欢 xml 的倾向（现在已经很少了）。  微信的很多 api 还是用 xml, 也许是出于这些原因。

xml 和 json 的区别，归根结底在于他们表达数据的方式不同，xml 用的是树形结构， json 对应的是 hash 映射。

## 使用工具测试 xml 数据接口

接口发送 xml 格式的数据和发送 json 几乎一样，只需要把格式改成 xml 就可以了。

采用 postman 接口测试工具 往接口`https://httpbin.org/post` 发送以下 xml 数据：
```
<note>
<to>you</to>
<from>yuz</from>
<heading>hey</heading>
<body>8 tonight</body>
</note>
```

postman 数据填写：



