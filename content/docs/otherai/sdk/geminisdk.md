---
weight: 2
bookFlatSection: true
title: "Gemini SDK配置"

seo_title: "Gemini SDK配置使用教程_国内如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

#Gemini SDK 配置
___

## 🌟 Gemini Python SDK 入门文档
---
### 🔧 1. 安装与设置
---
#### 获取 API 密钥

在网站 https://api.whatai.cc/token 获取令牌

#### 🚀 2. 生成简单文本
---
```
CUSTOM_BASE_URL // 网站 BaseURL 通常是域名
API_KEY // 令牌页获取的令牌
```

非流式

```
from google import genai
from google.genai import types

client = genai.Client(
    http_options=types.HttpOptions(
    base_url= CUSTOM_BASE_URL
),
    api_key= API_KEY
)

response = client.models.generate_content(
    model="gemini-2.5-flash",
    contents="How does AI work?"
)

print(response.text)
```