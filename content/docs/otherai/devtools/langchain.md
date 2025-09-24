---
weight: 5
bookFlatSection: true
title: "LangChain​"

seo_title: "LangChain​配置使用教程_国内如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# LangChain 
---

注意事项 ​
---

*   openai_api_base, 的末尾要加上, /v1/chat/completions, ，而且目前只支持 Chat 模型，请确认不要导入错误的包。

### 示例代码 ​
```python
from langchain.chat_models import ChatOpenAI

llm = ChatOpenAI(
    openai_api_base="https://api.whatai.cc/v1/chat/completions", 
    openai_api_key="sk-xxxxx",
)

res = llm.predict("hello")

print(res)

```
