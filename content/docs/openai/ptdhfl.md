---
weight: 2
bookFlatSection: true
title: "普通文本对话（非流）"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 普通文本对话（非流）


### **基础信息**



*   接口地址: https://api.whatai.cc

*   认证方式: Bearer Token (API Key)

#### **普通对话接口**

**POST 请求示例**

```python
import requests
import json

# 配置API参数
url = "https://api.whatai.cc/v1/chat/completions"  # API端点
payload = {
    "model": "gpt-4o-mini",  # 指定模型
    "messages": [
        {
            "role": "system",
            "content": "You are a helpful assistant."
        },
        {
            "role": "user",
            "content": "周树人和鲁迅是兄弟吗？"
        }
    ]
}
headers = {
    'Accept': 'application/json',
    'Authorization': 'sk-******',  # 替换为你的API Key
    'User-Agent': 'xxx/1.0.0',
    'Content-Type': 'application/json'
}

# 发送请求
response = requests.post(url, headers=headers, data=json.dumps(payload))
print(response.text)
```


#### **使用OpenAI官方SDK**
```
from openai import OpenAI

# 初始化客户端
client = OpenAI(
    api_key="sk-******",  # 替换为你的API Key
    base_url="https://api.whatai.cc/v1"  # API中转地址
)

# 创建对话
chat_completion = client.chat.completions.create(
    messages=[
        {
            "role": "user",
            "content": "周树人和鲁迅是兄弟吗？",
        }
    ],
    model="o1",  # 指定模型
)

print(chat_completion)

```


#### **注意事项**

1.   请妥善保管API Key，不要泄露

2.   所有请求必须通过HTTPS发送

3.   响应格式为JSON


