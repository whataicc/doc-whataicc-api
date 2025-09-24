---
weight: 3
bookFlatSection: true
title: "基本概念-API地址（BaseURL）"

seo_title: "基本概念-API地址（BaseURL）_如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

## 📖基本概念-API地址（BaseURL）

### 1️⃣ 基本概念

*   中转网址，用于替换官方API地址

*   官方地址：`https://api.openai.com` 需要被替换成 神马中转API地址：`https://api.whatai.cc`

*   所有地址数据互通

### **💻 API（BaseUrl）信息入口：**


**👉** [神马中转API工作台](https://api.whatai.cc/dashboard)

根据自己调用API的地理位置选择最优线路以获得最佳体验

部分路线可能区域网络受限，若无法正常访问API地址，请尝试更换地址

![Image 13](https://pic2.imgdd.cc/item/68cb9060fcdff6548300a561.png)



### **🔌 完整功能接口映射表**

| **功能** | **路径** | **完整示例URL** |
| --- | --- | --- |
| **智能对话** | /v1/chat/completions | https://api.whatai.cc/v1/chat/completions  |
| **文本嵌入** | /v1/embeddings | https://api.whatai.cc/v1/embeddings |
| **AI绘图** | /v1/images/generations |https://api.whatai.cc/v1/images/generations |
| **语音转文本** | /v1/audio/transcriptions | https://api.whatai.cc/v1/audio/transcriptions |
| **文本转语音** | /v1/audio/speech | https://api.whatai.cc/v1/audio/speech |

在 claude code 里只需要配置域名，不需要带 /v1及后面的部分。

**Python 示例**

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

需要先 pip install openai
```
import openai 
# 配置API密钥和基础URL 
openai.api_key = "sk-******" # 替换为你的实际令牌 
openai.api_base = "https://api.whatai.cc" # 设置中转地址# 

调用对话接口示例 
response = openai.ChatCompletion.create( 
    model="gpt-3.5-turbo",
    messages=[{"role": "user", "content": "你好"}] ) 
print(response.choices[0].message.content)
```
**curl 示例**
-----------
```
curl --request POST \
    --url https://api.whatai.cc/v1/chat/completions \
    --header 'Authorization: Bearer sk-替换为你的key' \
    -H "Content-Type: application/json" \
    --data '{
      "max_tokens": 8192,
      "model": "gpt-4.1-mini",
      "temperature": 0.8,
      "top_p": 1,
      "presence_penalty": 1,
      "messages": [
          {
              "role": "system",
              "content": "你是我的全能助手，你叫小美"
          },
          {
              "role": "user",
              "content": "你是谁？夸我几句我就给你续费~"
          }
      ]
  }'
```


