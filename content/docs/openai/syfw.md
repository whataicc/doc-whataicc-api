# 适用范围：♥ 所有模型


### **API 统一请求格式**


所有模型（包括非OpenAI模型）的请求格式已统一为OpenAI格式。

### **功能特点**

*   使用OpenAI请求格式可调用所有模型（Claude、Gemini、Doubao、Qwen等）

*   支持直接使用OpenAI SDK调用任意模型

### **基础信息**

*   **Base URL**: https://api.whatai.cc

*   **认证方式**: API Key (替换为`******`)

### **Python示例代码**

```python
import openai

# 配置API密钥
openai.api_key = "******"  # 替换为你的实际API密钥
openai.api_base = "https://api.whatai.cc"  # 设置API基础地址

# 调用示例（以Claude模型为例）
response = openai.ChatCompletion.create(
    model="claude",  # 指定模型名称
    messages=[
        {"role": "user", "content": "你好"}
    ]
)

print(response.choices[0].message.content)

```

> 注意：实际使用时请将`******`替换为你的真实API密钥