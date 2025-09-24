---
weight: 1
bookFlatSection: true
title: "基本概念-令牌（Token）"

seo_title: "基本概念-令牌（Token）_如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# 📖基本概念-令牌（Token）



### 1️⃣ 基本概念

*   别称：密钥、key、token

*   用于身份验证核心凭证，关联用户账户信息等

*   用户可自主管理令牌，支持以下操作

✅ 新增多个令牌

✅ 设置单令牌额度上限

✅ 指定调用渠道分组（如ssvip、default）

✅ 绑定调用模型权限

**📖 示例格式（非真实token）：**

`sk-UEE3xe6AgDeAvlCUQsP0hJSdyaOsNpByoMtb99CC8POogslU`

**💻 管理入口：**

**👉** [神马中转API令牌控制台](https://api.whatai.cc/token)


![Image 7](https://pic2.imgdd.cc/item/68cb7cc5fcdff654830097fd.png)


### **❓ 用户高频疑问解密**

**Q：如何获取 Openai Key？ 如何获取 Claude Key？ 如何获取 gemini key？**

→ A：Key就是令牌！这个key可以使用站内支持模型页面介绍的所有模型（260+），GPT系列模型、Claude系列模型、gemini系列模型等等等。

**Q：key为什么不能用？为什么我调用API没反应？**

→ A：大部分情况是 Base url设置不正确造成。需要把Openai的Baseurl改成 https://api.whatai.cc


**Q: 单个key的并发或RPM、TPM有限制吗？**

→ A：: 没有限制。神马中转API不会主动限制用户 RPM TPM ，但所有模型账号都是所有用户共享，遇到使用高峰可能会 429 或 500 报错。高并发需求用户可以寻找客服咨询。

* * *