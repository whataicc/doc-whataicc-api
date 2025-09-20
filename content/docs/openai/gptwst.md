---
weight: 11
bookFlatSection: true
title: "gpt文生图"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# gpt文生图

## **概念介绍**
--------

文生图(Text-to-Image)是一种通过自然语言描述生成对应图像的技术。本API基于OpenAI的GPT模型实现，支持多种图像生成模型和尺寸规格。

## **基础信息**
--------

*   请求方式: POST

*   Base URL: `https://api.whatai.cc`

*   接口路径: `/v1/images/generations`

*   认证方式: Bearer Token

## **请求参数**
--------

| **参数名** | **类型** | **必填** | **说明** |
| --- | --- | --- | --- |
| prompt | string | 是 | 图像描述文本 |
| n | int | 否 | 生成图片数量(默认1) |
| model | string | 否 | 模型选择(默认gpt-image-1) |
| aspect_ratio | string | 否 | 宽高比(如"16:9") |
| size | string | 否 | 图像尺寸(如"1024x1536") |
| seed | int | 否 | 随机种子(-1表示随机) |

## **支持的模型**
---------

*   `gpt-image-1`: 基础模型(支持1024x1024,1024x1536,1536x1024)

*   `seedream-3.0`: 国内最强，豆包团队开发，即梦3 AI绘图大模型。

*   `gpt-image-1`: Openai GPT 的画图模型，文本理解与图像生成深度融合，适合文字驱动型创作

*   `imagen4`: 谷歌的绘图模型，对标 gpt-image

*   `flux-kontext-max`: Black Forest Labs推出商业级精度的图像生成，满足专业设计需求

*   `flux-kontext-pro`: 支持文本+图像输入的上下文感知生成/编辑模型，控制更精准。

## **Python调用示例**
--------------
```python
import json
import requests

# API配置
API_KEY = "sk-********************"  # 替换为你的API密钥
API_URL = "https://api.whatai.cc/v1/images/generations"

# 请求参数
payload = {
    "prompt": "哪吒竖着大拇指，背景广告牌写着 API",  # 图像描述
    "n": 1,  # 生成数量 
    "model": "gpt-image-1",  # 使用基础模型
    "size": "1024x1536",  # 图像尺寸
    "seed": -1  # -1 代表随机种子
}

headers = {
    "Authorization": f"Bearer {API_KEY}",
    "Content-Type": "application/json"
}

try:
    # 发送POST请求
    response = requests.post(API_URL, json=payload, headers=headers)
    response.raise_for_status()  # 检查HTTP错误
    
    # 解析响应数据
    result = response.json()
    print(json.dumps(result, indent=4, ensure_ascii=False))
    
except requests.exceptions.RequestException as e:
    # 错误处理
    print(f"请求失败: {e}")
    if e.response:
        print(f"状态码: {e.response.status_code}")
        print(f"响应内容: {e.response.text}")

```


## **响应示例**
--------

图片返回`base64`需要转为png图片格式。

成功响应将返回包含生成图像信息的JSON对象，其中可能包含：

*   `data`: 图像数据数组

*   `url`: 图像访问URL(部分模型)

*   `b64_json`: Base64编码的图像数据

```
{
    "created": 1677664795,
    "data": [
        {
            "url": "https://.../generated-image.png",
            "b64_json": "..." 
        }
    ]
}
```

## **常见错误码：**
----------

*   401: 认证失败(无效API密钥)

*   400: 请求参数错误

*   429: 请求频率限制

*   500: 服务器内部错误

建议在代码中添加完善的错误处理逻辑，如示例中所示。

## **详细教程**神马中转
--------

### **🎨 神马中转API 2025超强画图模型天团驾到！**

> "不会画画的API不是好艺术家" - **神马中转API**用户如是说

欢迎来到《手把手教你玩转AI画图》！这里有一群身怀绝技的"数字达芬奇"，随你调遣~

* * *

### **🌟 模型天团简历（2025顶配版）**

| **模特名** | **后台大佬** | **必杀技** | **身价（每张）** |
| --- | --- | --- | --- |
| **seedream-3.0** | 字节跳动豆包 | 文生图闪电侠⚡️ | ￥0.08 (~免费10万张!) |
| **gpt-image-1** | OpenAI | 改图/合图魔术师🎩 | ￥1+ |
| **imagen4** | 谷歌 | GPT-image的宿敌👊 | 待定 |
| **flux-kontext** | Black Forest | 商业级精修大师🖋️ | ￥0.2~0.4 |

> 📌 **温馨提示**：
> 
> 不同模特在不同场景表现迥异，建议多约会试试~（比如seedream适合批量创作，gpt-image擅长精修）

### **🚀 上车指南**

1️⃣ **领钥匙**：在 https://api.whatai.cc/token 获取API密钥

2️⃣ **选车站**：

```
API_HOST = "api.whatai.cc"
```
### **💫 模特A：seedream-3.0（文生图小旋风）**

```python
import base64, http.client, json, os, time

# 配置你的魔法棒🔮
API_KEY = "sk-******"  # 此处填你的阿拉丁神灯密码
prompt = "漫画风格英语学习图：Hello单词记忆引导"  # 你的脑洞有多大，舞台就有多大！
size = "1664x936"  # 常用尺寸任选：16:9(宽屏) | 1:1(Ins风) | 9:16(手机壁纸)

# 开始召唤！
conn = http.client.HTTPSConnection("api.whatai.cc")
conn.request("POST", "/v1/images/generations", json.dumps({
    "prompt": prompt,
    "model": "seedream-3.0",
    "size": size,
    "response_format": "b64_json"  # 必选！否则收不到图片快递
}), headers={"Authorization": f"Bearer {API_KEY}"})

# 拆快递啦~
res = conn.getresponse()
if res.status == 200:
    img_data = json.loads(res.read())["data"][0]["b64_json"]
    with open(f"seedream_{int(time.time())}.png", "wb") as f:
        f.write(base64.b64decode(img_data))
    print("🎉 你的大作已空投到文件夹！")
else:
    print(f"❌ 模特罢工了：{res.status} {res.reason}")


```

> 💡 **冷知识**：当前免费额度能生成10万张图，够你把《蒙娜丽莎》画成表情包全集！

### **🎩 模特B：gpt-image-1（PS战神）**

```python
import requests

# 准备整容手术台
api_key = "sk-******"
files = [
    ("image", ("原图.jpg", open("哪吒.jpg", "rb"), "image/jpeg")),  # 要改造的对象
    # ("image", ("背景.jpg", ...))  # 多图合并时加此项
]
payload = {"prompt": "给哪吒戴上炫酷红色鸭舌帽"}  # 你的改造指令

# 开始施法！
r = requests.post(
    "https://api.whatai.cc/v1/images/edits",
    headers={"Authorization": f"Bearer {api_key}"},
    files=files,
    data=payload
)

# 见证奇迹时刻✨
if r.status_code == 200:
    img_data = r.json()["data"][0]["b64_json"]
    with open("潮酷哪吒.png", "wb") as f:
        f.write(base64.b64decode(img_data))
    print(

```

### **🌟 模特C：flux-kontext（商业级精修大师）**

```python
import requests
import os
import base64
from time import sleep

# 准备你的魔法工具箱🛠️
API_KEY = "sk-******"  # 你的专属魔法通行证
target_img = "沙漠.jpg"  # 需要点石成金的照片

print("🔮 正在召唤商业级修图精灵flux-kontext...")
sleep(1)  # 加点魔法特效等待时间

try:
    # 开始施展专业级图像魔法
    response = requests.post(
        "https://api.whatai.cc/v1/images/edits",  # 国际站小伙伴请用.com
        headers={"Authorization": f"Bearer {API_KEY}"},
        files=[("image[]", (os.path.basename(target_img), open(target_img, "rb"), "image/jpeg"))],
        data={
            "model": "flux-kontext-max",  # 可选：flux-kontext-pro（速度型）｜ flux-kontext-max（质量型）
            "prompt": "给沙漠照片添加绿洲和彩虹",  # 你的想象力是唯一的限制
            "quality": "high"  # 品质选项：low（快但糙）｜ medium｜ high（慢但精）
        }
    )
    
    # 检查魔法是否生效
    if response.status_code == 200:
        print("🌈 魔法生效中...专业精灵正在精修您的照片")
        img_data = response.json()["data"][0]["b64_json"]
        
        # 保存你的魔法杰作
        with open("沙漠奇迹.jpg", "wb") as f:
            f.write(base64.b64decode(img_data))
        print("🎨 专业级大片已生成！建议立即设为壁纸炫耀~")
        
    else:
        print(f"🧙‍♂️ 啊哦，魔法失灵了！错误代码：{response.status_code}")
        print(f"🔍 详细原因：{response.text[:100]}...")  # 显示部分错误信息

except Exception as e:
    print(f"⚠️ 魔法反噬警告：{str(e)}")
    print("💡 小贴士：检查图片路径 | 网络连接 | API密钥有效性")

finally:
    print("✨ 本次魔法仪式结束，期待您下次召唤！")

```

> **专业小贴士**：
> 
> 
> 1.   `flux-kontext-pro`和`flux-kontext-max`就像魔法学徒和魔法大师——前者快，后者强
> 
> 2.   遇到复杂魔法（大图精修）时，喝杯咖啡耐心等待☕️
> 
> 3.   `quality`参数是质量与速度的平衡术，按需调配

### **❤️ 真爱提示**

1.   **密钥保管**：千万别把`sk-***`发到网上，否则你的AI模特会被别人拐跑！

2.   **错误处理**：遇到错误先检查——

*   ✔️ 域名写对了吗？

*   ✔️ 图片路径正确吗？

*   ✔️ 免费额度用完啦？

1.   **玩得开心**：多尝试不同咒语(prompt)，你会打开新世界大门！

> 最后，神马中转API团队为你打Call："让每个创意都轻松落地，是我们不变的初心~ ✨"

### **🎉 毕业典礼 & 防坑指南**

```python
# 所有模特通用的生存法则
print("""
🌟 三大黄金定律  🌟
1. 密钥保管好 -> 别让sk-***出现在GitHub上！
2. 域名要选对 -> .cn还是.com？错配会变404幽灵👻
3. 尺寸看清楚 -> 别让16:9的美图硬塞进1:1相框！
""")

print("🎓 恭喜你完成AI画图大师课程！现在去征服世界吧~")


```



✨ 教程到此结束，但你的创作之旅才刚刚开始！快去生成你的第一幅AI杰作吧~