---
weight: 7
bookFlatSection: true
title: "Claude API格式兼容"

seo_title: "本地图片解析_如何使用OpenAI中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---


# 神马中转API实现任意模型Claude Compatible接入！
---

随着 Claude Code 在开发者中的普及，越来越多的用户希望能在只支持 Claude 接口的应用中调用更多模型。神马中转API 率先实现了“任意模型 Claude Compatible”，极大推动了 AI 生态的开放和互联！

* * *

## 🧠 Claude 格式 vs OpenAI 格式对比
---

### 🎯 请求路径区别

| 接口类型 | 示例请求路径 |
| --- | --- |
| OpenAI 格式 | `api.whatai.cc/v1/chat/completions` |
| Claude 格式 | `api.whatai.cc/v1/messages` |

### 🧾 请求体格式差异

**OpenAI 格式请求示例**：

```json
{
    "model": "gpt-4.1",
    "messages": [
        {
            "role": "user",
            "content": "Hello!"
        }
    ]
}

```

**Claude 格式请求示例**：

```json
{
    "model": "claude-3-5-sonnet-20240620",
    "max_tokens": 1024,
    "messages": [
        {
            "role": "user",
            "content": "Hello, world"
        }
    ]
}
```

**关键差异**：

*   **参数结构**：Claude 请求中必须显式指定 `max_tokens`；OpenAI 中为可选。

*   **字段命名**：如 `messages` 等字段虽然类似，但默认行为及语义略有差异。

* * *

## 📦 响应格式差异对比
---

### OpenAI 返回示例

```json
{
    "choices": [
        {
            "finish_reason": "stop",
            "index": 0,
            "logprobs": null,
            "message": {
                "annotations": [],
                "content": "Hello! How can I assist you today? 😊",
                "refusal": null,
                "role": "assistant"
            }
        }
    ],
    "created": 1753384149,
    "id": "chatcmpl-BwvbRo5aJ8TXqFwmmOXsE7eicJig3",
    "model": "gpt-4.1",
    "object": "chat.completion",
    "system_fingerprint": "fp_07e970ab25"
}
```

### Claude 返回示例

```json
{
    "id": "msg_01NufbyqybJo5fVtRkH1VPzk",
    "type": "message",
    "role": "assistant",
    "model": "claude-3-5-sonnet-20240620",
    "content": [
        {
            "type": "text",
            "text": "Hello! How can I assist you today? Is there anything specific you'd like to talk about or any questions you have?"
        }
    ],
    "stop_reason": "end_turn"
}
```

**主要结构差异**：

| 项目 | OpenAI | Claude |
| --- | --- | --- |
| 回复结构 | 使用 `choices` 数组 | 顶层 `content` 数组 |
| 内容位置 | `choices[0].message.content` | `content[0].text` |
| 元信息 | 包括 `created`, `id`, `model` 等 | 命名结构不同但信息类似 |
| 停止标识 | `finish_reason` | `stop_reason` |

* * *

## 🚧 接口不兼容性的挑战
---

虽然两者都使用 JSON 结构，但在：

*   **流式响应**

*   **函数调用**

*   **系统提示词的结构**

*   **返回格式嵌套层级**

等方面存在较大差异，导致 OpenAI 与 Claude 的 API 完全不兼容。

* * *

## 🚀 神马中转API：让任意模型秒变 Claude Compatible！
---

为解决这一痛点，神马中转API 推出了革命性的 API 中转兼容方案：

*   ✅ **兼容 Claude Code 接口标准**

*   ✅ **支持平台自营全部模型**

*   ✅ **支持接入自定义第三方模型**

*   ✅ **统一封装为 Claude 格式，自动协议转换**

### 🌐 一站式模型整合平台

开发者可将任何模型（无论底层是否兼容 Claude 格式）通过神马中转API 的“自定义 API 功能”接入平台。神马中转API将自动完成协议适配，统一转化为 Claude Compatible 接口，无需手动修改代码。

* * *


## 🌈 总结：连接模型生态的桥梁
---

神马中转API 打破了模型协议的壁垒，让所有模型都能：

*   **被 Claude Code 等工具无缝调用**

*   **灵活集成进任何只支持 Claude 的应用**

*   **降低开发和迁移成本，提升跨平台效率**

未来 AI 世界的“多模型互联”将成为常态，而神马中转API 正在为此铺平道路。

* * *

如果你希望在 Claude Code 或其他仅支持 Claude 接口的环境中使用更多模型，现在就是最佳时机。

> 🧩 **即刻开启 Claude Compatible 模型整合之旅，让所有模型为你所用！**
