---
weight: 5
bookFlatSection: true
title: "高级功能-官方SDK支持"

seo_title: "高级功能-官方SDK支持_如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 高级功能-官方SDK支持


### **支持的厂商**

*   OpenAI SDK

*   Anthropic Claude SDK

*   Google Gemini SDK

### **配置方法**

只需修改 SDK 的 Key 和 Base Url 即可使用

```python
# 初始化 OpenAI 客户端
client = OpenAI(
    api_key="sk-********************************",  # 替换为你的神马中转api 令牌key
    base_url="https://api.whatai.cc/v1",  # 使用 神马中转API 中转地址
)

# 示例调用
response = client.chat.completions.create(
    model="gpt-4.1-mini",
    messages=[{"role": "user", "content": "Hello!"}]
)
print(response.choices[0].message.content)
```


> 提示：将 `******` 替换为你实际的 API Key，其他厂商 SDK 配置方式类似