---
weight: 4
bookFlatSection: true
title: "固定格式化输出Json"

seo_title: "固定格式化输出Json_如何使用OpenAI中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 固定格式化输出Json


### **格式化输出 接口说明**


通过OpenAI API获取产品信息，返回JSON格式数据。

### **请求地址**


`POST https://api.whatai.cc/v1/chat/completions`

### **请求参数**


#### **Headers**


| **参数名** | **类型** | **必填** | **说明** |
| --- | --- | --- | --- |
| Authorization | string | 是 | API密钥，格式: `Bearer ******` |
| Content-Type | string | 是 | 固定值: `application/json` |

#### **Body**

```json
{
  "model": "gpt-4o-2024-08-06",
  "messages": [
    {
      "role": "system",
      "content": "根据给出的产品进行分析，按json格式用中文回答,json format:product_name, price, description."
    },
    {
      "role": "user",
      "content": "产品描述"
    }
  ],
  "response_format": {
    "type": "json_object"
  }
}
```


### **Python示例代码**


```python
from pydantic import BaseModel
from openai import OpenAI
from dotenv import load_dotenv
import json
from textwrap import dedent

# 加载环境变量，例如 API key 等配置信息
load_dotenv()

# 设置 OpenAI API 的工厂名称，默认为 "openai"
factory = "openai"

# 初始化 OpenAI 客户端，传入 API key 和 base URL
client = OpenAI(
    api_key="sk-***********************************************",  # 替换为你的 API key
    base_url="https://api.whatai.cc/v1/"   # 这里是 base url，注意这里需要 /v1/
)

# 定义一个产品信息类，用于解析 API 返回的数据
class ProductInfo(BaseModel):
    product_name: str  # 产品名称，字符串类型
    price: float  # 价格，浮点数类型
    description: str  # 产品描述，字符串类型

# 定义一个提示信息，用于请求模型返回 JSON 格式的产品信息
product_prompt = '''根据给出的产品进行分析，按json格式用中文回答,json format:product_name, price, description.'''

# 获取产品信息的函数，传入用户的问题
def get_product_info(question: str):
    # 使用 OpenAI 客户端进行聊天模型的请求
    completion = client.beta.chat.completions.parse(
        model="gpt-4o-2024-08-06",  # 指定使用的模型
        messages=[
            {"role": "system", "content": dedent(product_prompt)},  # 发送系统消息，设置模型的行为
            {"role": "user", "content": question},  # 发送用户消息，用户提出问题
        ],
        response_format=ProductInfo,  # 指定返回的数据格式为 ProductInfo
    )

    # 返回模型解析的第一个选项的消息结果
    return completion.choices[0].message.parsed

# 初始化一个空的产品信息字典
product_inform = {}

# 定义将解析的结果转换为 JSON 的函数
def transform2JSON(parsed_result):
    # print(parsed_result)  # 打印解析结果

    # 将解析的结果存储到字典中
    product_inform["product_name"] = parsed_result.product_name
    product_inform["price"] = parsed_result.price
    product_inform["description"] = parsed_result.description

    # 将字典转换为 JSON 字符串并返回，ensure_ascii=False 允许中文字符正常显示
    return json.dumps(product_inform, ensure_ascii=False, indent=4)

# 定义用户输入的问题，即一个产品信息的描述
question = "75寸小米电视机"

# 调用函数获取产品信息
result = get_product_info(question)


# 将解析结果转换为 JSON 格式并打印
json_result = transform2JSON(result)
print(json_result)
```

### **返回示例**
```json
{
    "product_name": "小米电视75寸",
    "price": 4999.0,
    "description": "4K超高清画质，支持HDR，内置小爱同学语音助手"
}
```

### **注意事项**

1.   请妥善保管API密钥

2.   产品信息由AI生成，仅供参考