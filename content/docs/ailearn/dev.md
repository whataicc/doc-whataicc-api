#基础教程-开发者 · 快速接入


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