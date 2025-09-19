# 函数调用FunctionCall



## **概念介绍**

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

函数调用(Function Calling\Tools Calling)是AI大模型的一种能力。允许大语言模型在对话过程中调用外部函数/工具。当用户提问需要实时数据(如天气、股票等)时，模型会返回函数调用请求，开发者可以在后端执行相应函数并返回结果。

## **API 基础信息**


---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

*   请求地址: `https://api.whatai.cc/v1/chat/completions`

*   请求方法: POST

*   认证方式: Bearer Token

## **请求示例**


-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

```python
import http.client
import json

# 创建HTTPS连接
conn = http.client.HTTPSConnection("api.whatai.cc")

# 构造请求体
payload = json.dumps({
    "model": "gpt-4o",  # 指定模型
    "max_tokens": 300,  # 最大返回token数
    "temperature": 0.8,  # 生成结果的随机性控制
    "stream": False,  # 是否流式输出
    "messages": [{
        "role": "user",
        "content": "上海今天几度？"  # 用户提问
    }],
    "tools": [{  # 定义可用工具
        "type": "function",
        "function": {
            "name": "get_current_weather",  # 函数名称
            "description": "获得天气信息",  # 功能描述
            "parameters": {  # 参数定义
                "type": "object",
                "properties": {
                    "location": {  # 必填参数：地点
                        "type": "string",
                        "description": "城市和州名，例如：上海, 中国"
                    },
                    "unit": {  # 可选参数：温度单位
                        "type": "string",
                        "enum": ["celsius", "fahrenheit"]
                    }
                },
                "required": ["location"]  # 必填参数列表
            }
        }
    }]
})

# 请求头设置
headers = {
    "Accept": "application/json",
    "Authorization": "Bearer sk-**********************",  # 替换为你的 API 令牌
    "Content-Type": "application/json"
}

# 发送请求
conn.request("POST", "/v1/chat/completions", payload, headers)

# 获取响应
res = conn.getresponse()
data = res.read()

# 输出结果
print(data.decode("utf-8"))

```

## **响应处理**

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

当用户提问需要调用函数时，API会返回包含函数调用信息的JSON响应。开发者需要：

1.   解析响应中的函数调用请求

2.   在后端执行对应函数

3.   将函数结果再次发送给API获取最终回答

## **注意事项**

-------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.   请妥善保管API密钥，不要泄露

2.   函数定义中的description很重要，会影响模型是否/如何调用该函数

3.   温度参数(temperature)控制生成结果的随机性，值越大结果越多样

## Tools 场景示例
==========

例如

用户提问：**“北京天气怎么样？”**

我们定义一个工具 `get_weather(city: string)`

`get_weather` 函数需要用户开发者自己实现

* * *

✅ 第一步：发送用户提问 + 工具定义
-------------------

```

curl --location --request POST 'https://api.whatai.cc/v1/chat/completions' \
--header 'Authorization: Bearer $API_KEY' \
--header 'Content-Type: application/json' \
--data-raw '{
    "model": "gpt-4o",
    "messages": [
        {
            "role": "user",
            "content": "北京天气怎么样？"
        }
    ],
    "tools": [
        {
            "type": "function",
            "function": {
                "name": "get_weather",
                "description": "获取城市天气",
                "parameters": {
                    "type": "object",
                    "properties": {
                        "city": {
                            "type": "string",
                            "description": "城市名称，例如 北京"
                        }
                    },
                    "required": [
                        "city"
                    ]
                }
            }
        }
    ],
    "tool_choice": "auto"
}'
```

📥 AI 返回内容（模型决定调用 `get_weather`）：

```
{
  "choices": [
    {
      "message": {
        "role": "assistant",
        "tool_calls": [
          {
            "id": "toolcall-abc123",
            "type": "function",
            "function": {
              "name": "get_weather",
              "arguments": "{ \"city\": \"北京\" }"
            }
          }
        ]
      }
    }
  ]
}

```

🔁 第二步：你执行实际函数（例如自己写的天气 API），并将结果通过工具响应发回 AI
--------------------------------------------

假设你查询天气后得到：

`{ "temperature": "31°C", "condition": "晴" }`

那么你现在发送的是 **完整上下文 + tool 响应**：

```

curl --location --request POST 'https://api.whatai.cc/v1/chat/completions' \
--header 'Authorization: Bearer $API_KEY' \
--header 'Content-Type: application/json' \
--data-raw '{
    "model": "gpt-4o",
    "messages": [
        {
            "role": "user",
            "content": "北京天气怎么样？"
        },
        {
            "role": "assistant",
            "tool_calls": [
                {
                    "id": "toolcall-abc123",
                    "type": "function",
                    "function": {
                        "name": "get_weather",
                        "arguments": "{ \"city\": \"北京\" }"
                    }
                }
            ]
        },
        {
            "role": "tool",
            "tool_call_id": "toolcall-abc123",
            "content": "{ \"temperature\": \"31°C\", \"condition\": \"晴\" }"
        }
    ]
}'
```

* * *

✅ 第三步：返回最终的自然语言回复（例如）：
----------------------

```
{
    "choices": [
        {
            "message": {
                "role": "assistant",
                "content": "北京今天是晴天，气温为 31°C。适合出门哦！"
            }
        }
    ]
}
```

[https://doc.dmxapi.cn/base64-image.html](https://doc.dmxapi.cn/base64-image.html)

![Image 8](https://wiki.bltcy.ai/node/01983608-3d61-718c-89db-db78937a9575)