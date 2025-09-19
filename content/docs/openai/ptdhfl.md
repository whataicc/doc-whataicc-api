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


