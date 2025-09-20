---
weight: 4
bookFlatSection: true
title: "基础教程-开发者 · 快速接入"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---
# 基础教程-开发者 · 快速接入


### **基础信息**


*   Base URL: https://api.whatai.cc

*   认证方式: Bearer Token (API Key)

**更多baseURL👉： 基础概念-API地址（BaseUrl）**

### **文本对话接口**


**请求**



*   方法: POST

*   路径: `/v1/chat/completions`

*   Headers:

    *   `Accept`: application/json

    *   `Authorization`: Bearer sk-****** (你的API Key)

    *   `User-Agent`: DMXAPI/1.0.0 (https://api.whatai.cc)

    *   `Content-Type`: application/json

### **请求参数**

```json
{
  "model": "gpt-4o-mini",
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
```

### **cURL 示例**


```bash
curl -X POST "https://api.whatai.cc/v1/chat/completions" \
  -H "Accept: application/json" \
  -H "Authorization: Bearer sk-******" \  # 替换为你的API Key
  -H "User-Agent: DMXAPI/1.0.0" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-4o-mini",
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
  }'
```


### **Python 示例**

```python
import requests
import json

# API配置
url = "https://api.whatai.cc/v1/chat/completions"
headers = {
    'Accept': 'application/json',
    'Authorization': 'Bearer sk-******',  # 替换为你的API Key
    'User-Agent': 'DMXAPI/1.0.0',
    'Content-Type': 'application/json'
}

# 请求数据
payload = json.dumps({
    "model": "gpt-4o-mini",
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
})

# 发送请求
response = requests.post(url, headers=headers, data=payload)

# 输出响应
print(response.text)
```


### **响应**

返回JSON格式的对话结果

提示：将示例中的`sk-******`替换为你实际的API Key即可使用