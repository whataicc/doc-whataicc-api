---
weight: 2
bookFlatSection: true
title: "python openai官方库（使用AutoGPT，langchain等）"

seo_title: "python openai官方库（使用AutoGPT，langchain等）_国内如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---


### **python openai官方库（使用AutoGPT，langchain等）**



***方法一***

```python
import openai
openai.api_base = "https://api.whatai.cc/v1"
```

***方法二（方法一不起作用用这个）***

修改环境变量OPENAI_API_BASE，各个系统怎么改环境变量请自行搜索，修改环境变量后不起作用请重启系统。

```sh
OPENAI_API_BASE=https://api.whatai.cc/v1
```


