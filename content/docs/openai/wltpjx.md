---
weight: 6
bookFlatSection: true
title: "网络图片解析"

seo_title: "网络图片解析_如何使用OpenAI中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 网络图片解析
---

## **接口说明**
---

通过多模态AI模型分析图片内容，理解图片、提取图片信息，包括OCR功能。

## **主流图片分析模型**
---
| **模型名称** | **描述** |
| --- | --- |
| gpt-4o | 目前图片分析调用量最大的模型，稳定、并发高 |
| gemini-2.5-flash | 谷歌旗舰模型，速度快，性价比好 |
| claude-sonnet-4-20250514 | 图片分析做的不错，但性价比略差 |
| doubao-1.5-vision-pro-250328 | 国内图片分析主流模型，性价比好，稳定、并发高 |

## **基础信息**
---

*   **Base URL**: https://api.whatai.cc

*   **请求方式**: POST

*   **Content-Type**: `application/json`

## **接口地址**
---

POST `/v1/chat/completions`

## **请求头**
---

| **参数** | **类型** | **必填** | **说明** |
| --- | --- | --- | --- |
| Authorization | string | 是 | Bearer token，格式：`Bearer ******` |
| Content-Type | string | 是 | 固定值：`application/json` |
| User-Agent | string | 否 | 客户端标识 |

## **请求参数**
---

```json
{
  "model": "gemini-2.0-flash-thinking-exp-1219",
  "messages": [
    {
      "role": "system",
      "content": [
        {"type": "text", "text": "你是一个图片分析助手。"}
      ]
    },
    {
      "role": "user",
      "content": [
        {
          "type": "image_url",
          "image_url": {
            "url": "图片URL"
          }
        },
        {
          "type": "text",
          "text": "分析提示词"
        }
      ]
    }
  ],
  "temperature": 0.1,
  "user": "whatai"
}
```

## **参数说明**
---

| **参数** | **类型** | **必填** | **说明** |
| --- | --- | --- | --- |
| model | string | 是 | 模型名称，推荐：`gemini-2.5-flash` 或 `gpt-4o` |
| messages | array | 是 | 消息内容数组 |
| temperature | float | 否 | 生成文本的随机性，0-1之间 |
| user | string | 否 | 用户标识 |

## **Python 调用示例**

```python
import requests

# API配置
BASE_URL = "https://api.whatai.cc/"
API_ENDPOINT = BASE_URL + "v1/chat/completions"
API_KEY = "sk-******"  # 替换为你的API密钥
IMAGE_URL = "https://api.whatai.cc/111.jpg"  # 替换为你的图片URL

def analyze_image(image_url, prompt):
    """
    图片分析函数
    :param image_url: 图片URL
    :param prompt: 分析提示词
    :return: 分析结果文本
    """
    payload = {
        "model": "gemini-2.0-flash-thinking-exp-1219",
        "messages": [
            {
                "role": "system",
                "content": [{"type": "text", "text": "你是一个图片分析助手。"}]
            },
            {
                "role": "user",
                "content": [
                    {"type": "image_url", "image_url": {"url": image_url}},
                    {"type": "text", "text": prompt}
                ]
            }
        ],
        "temperature": 0.1
    }
    
    headers = {
        "Content-Type": "application/json",
        "Authorization": f"Bearer {API_KEY}"
    }

    try:
        response = requests.post(API_ENDPOINT, headers=headers, json=payload)
        response.raise_for_status()
        return response.json()["choices"][0]["message"]["content"]
    except Exception as e:
        print(f"请求失败: {e}")
        return None

# 使用示例
if __name__ == "__main__":
    result = analyze_image(IMAGE_URL, "请描述这张图片的内容")
    if result:
        print("分析结果:", result)

```

## **常见错误码**
---

| **状态码** | **说明** |
| --- | --- |
| 400 | 请求参数错误，看看图片是不是太大了 |
| 500 | 服务器内部错误 |