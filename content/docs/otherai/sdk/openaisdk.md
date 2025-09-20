---
weight: 1
bookFlatSection: true
title: "OpenAI官方SDK"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# OpenAI官方SDK ​
---
## 使用 OpenAI API 查询 GPT-4 
---
以下是一个示例代码，演示如何使用 OpenAI API 查询 GPT-4 模型的回答。

### 示例代码 ​
---
```python
import openai

def query_gpt4(question):
    openai.api_key = "sk-xxx"  # 替换为您的 API 密钥
    # openai.base_url = url
    openai.base_url = 'https://api.whatai.cc/v1/'  # 设置 API 基础 URL

    try:
        response = openai.chat.completions.create(
            model="gpt-4",  # 确认使用 GPT-4 模型
            messages=[
                {"role": "system", "content": "You are a helpful assistant."},
                {"role": "user", "content": question}
            ]
        )
        print(response)  # 打印完整的响应
        return response['choices'][0].message['content']  # 返回 GPT-4 的回答
    except Exception as e:
        return str(e)  # 返回错误信息

# 问题
question = "为什么太阳那么红？"

# 获取并打印回答
answer = query_gpt4(question)
print(answer)

```

### 注意事项 ​
---
>确保您替换, sk-xxx, 为您的有效 API 密钥。
>
>使用正确的 API 基础 URL，并根据需要修改其他设置。