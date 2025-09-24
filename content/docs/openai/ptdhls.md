---
weight: 3
bookFlatSection: true
title: "普通文本对话（流式输出）"

seo_title: "普通文本对话（流式输出）_如何使用OpenAI中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 普通文本对话（流式输出）


### **基础信息**


*   接口地址: https://api.whatai.cc

*   认证方式: Bearer Token (API Key)

### **请求参数**

| **参数** | **类型** | **说明** |
| --- | --- | --- |
| model | string | 模型名称(如gpt-4o-mini) |
| stream | boolean | 是否开启流式输出 |
| messages | array | 对话消息列表 |

### **Python 请求示例**

```python
import json
import requests

# 配置请求参数
url = "https://api.whatai.cc/v1/chat/completions"
headers = {
    "Authorization": "Bearer sk-******",  # 替换为你的API Key
    "Content-Type": "application/json"
}
payload = {
    "model": "gpt-4o-mini",
    "stream": True,  # 开启流式输出
    "messages": [
        {"role": "system", "content": "You are a helpful assistant."},
        {"role": "user", "content": "周树人和鲁迅是兄弟吗？"},
    ]
}

# 发送请求并处理流式响应
response = requests.post(url, headers=headers, json=payload, stream=True)
buffer = ""

for chunk in response.iter_content(chunk_size=None):
    if chunk:
        buffer += chunk.decode("utf-8")
        while "\n" in buffer:
            line, buffer = buffer.split("\n", 1)
            if not line.strip():  # 跳过空行
                continue
                
            if line.startswith("data: "):
                data_line = line[6:].strip()  # 去除"data: "前缀
                
                if data_line == "[DONE]":  # 流式结束标记
                    break
                    
                try:
                    data = json.loads(data_line)
                    # 提取并打印响应内容
                    content = data["choices"][0]["delta"].get("content", "")
                    print(content, end="", flush=True)
                except json.JSONDecodeError:
                    # 处理不完整JSON数据
                    buffer = line + "\n" + buffer
                    break
```

### **注意事项**

1.   请妥善保管API Key

2.   建议使用HTTPS协议

3.   响应格式为JSON