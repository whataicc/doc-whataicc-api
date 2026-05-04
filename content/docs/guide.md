---
title: "快速使用指南"
date: 2023-11-26T17:30:00+08:00
draft: false
description: "三步快速接入神马中转API，完全兼容OpenAI接口"
weight: 2
---

## 🖥️ 1、注册「神马中转API」账号

**免费注册**：注册将自动赠送 **0.2 美金余额**，测试阶段跑通绝对没问题，首页工作台也有签赠送额度~

[立即注册](https://api.whatai.cc/login)

---

## 🔑 2、获得 API Key

进入后台的 **[令牌](https://api.whatai.cc/token)** 页面，选择右上角【添加令牌】，填写名称其他默认，即可获取生成的key

Key 的格式通常是：`sk-xxxx......`

[添加令牌详细教程](https://docs.whatai.cc/docs/aidocs/key/)

---

## 🔄 3、修改代码的请求地址

### 调用方式
只需要将请求地址和 Key 修改为与 OpenAI 官方完全一致。

简单来说：将 `https://api.openai.com` 全局替换改成：
`https://api.whatai.cc`

并使用在『神马中转API』网站后台的 **令牌**，其他代码层面无需做任何改动。

### 模型方面
本站支持大部分OpenAI、Claude、Gemini、Nano Banana等可用模型，注册即可试用。

[账户菜单 > 模型价格 > 一键复制模型名称](https://api.whatai.cc/models)

### 注意事项
不同的客户端需要填写不同的BASE_URL，某些程序需要添加 `v1` 后缀，具体有3种情况，请测试：

* `https://api.whatai.cc` 
* `https://api.whatai.cc/v1`
* `https://api.whatai.cc/v1/chat/completions`


## 神马中转API可视化操作演示

顶部菜单选择聊天，里面有可视化操作【聊天&画图&视频&音乐】【Nano Banner画图】【GPT画图】【操练场】

### Nano Banner画图

默认配置，选择文生图或者图生图，输入提示词、选择数量/质量/比例，点击【生成】，等待生成完成第一时间下载图片不要刷新页面。

选择模型可以点击右上方齿轮，里面选择模型：

* Nano Banana 2：Gemini 3.1 Flash Image（预览版）模型 (gemini-3.1-flash-image-preview)。此模型是 Gemini 3 Pro Image 的高效版本，针对速度和高用量开发者使用情形进行了优化。
* Nano Banana Pro：Gemini 3 Pro Image 预览版模型 (gemini-3-pro-image-preview)。此模型专为专业资产制作而设计，利用高级推理（“思考”）功能来遵循复杂的指令并呈现高保真文本。
* Nano Banana：Gemini 2.5 Flash Image 模型 (gemini-2.5-flash-image)。此模型专为速度和效率而设计，经过优化，可处理海量低延迟任务。


**页面上的余额张数都不用管，是错误的，可以正常使用**

![AI中转站教程原理_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/6927b5d7c828c4c6deffdc00.png)

### 聊天&画图&视频&音乐

默认配置，选择模型，是输入问题，发送等待回复

更多详细教程：[聊天详细教程](https://docs.whatai.cc/docs/otherai/chat/chatgptwebmidjourneyproxy/)
![AI中转站教程原理_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/6927b7adc828c4c6deffdca9.png)



### GPT Image 2绘图

路径：顶部菜单-聊天-【GPT-Image-2绘图】

进入之后右上角设置超时时间：1200秒

![AI中转站教程原理_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/69f82c111b404a7cc77423f6.webp)



### 操练场-终极测试所有模型

操练场，正常默认配置，选择模型，输入问题，发送

每次请求前点击输入框旁边的垃圾桶，清除内容之后在使用
![AI中转站教程原理_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/691fdb85c828c4c6defabc03.png)

如果需要传图片可以随便找个免费图床即可，推荐[聚合图床](https://www.superbed.cc/signup?link=1827pfhr)
![AI中转站教程原理_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/6927bbb8c828c4c6deffe173.png)

### 机灵助手
也可以去基于神马中转API开发的微信小程序使用gpt-image-2、NanoBanana生图，新用户赠送1000

![AI生图微信小程序推荐机灵助手_AI大模型API中转聚合站推荐_神马API中转](https://pic.imgdd.cc/item/69f82d211b404a7cc7742457.png)

## 快速教程

### API文档常用接口
[聊天兼容OPENAI格式接口（gpt、Gemini、Claude等）](hhttps://gpt-best.apifox.cn/doc-6113929)

[通用gpt-image-2绘图开发API接口（gpt-image-2等绘图）](https://gpt-best.apifox.cn/api-447261009)

[通用绘图异步API接口（Nano-banana、gpt-image等）](https://gpt-best.apifox.cn/api-356258955)

[通用视频开发API接口（Sora、veo等）](https://gpt-best.apifox.cn/doc-7324259)

[神马中转API开发文档](https://gpt-best.apifox.cn/)


### 常用软件教程
[OpenClaw安装配置教程](https://docs.whatai.cc/docs/otherai/tools/openclaw)

[Claude Code保姆级新手安装使用教程](https://docs.whatai.cc/docs/otherai/devtools/claudecode/)

[CodeX配置使用教程](https://docs.whatai.cc/docs/otherai/devtools/codex/)

[Chatbox教程快速安装与使用](https://docs.whatai.cc/docs/otherai/chat/chatbox/)

[Cherry Studio安装配置使用教程](https://docs.whatai.cc/docs/otherai/chat/cherrystudio/)

[VSCode插件Cline配置使用教程](https://docs.whatai.cc/docs/otherai/devtools/cline/)

[N8N教程](https://docs.whatai.cc/docs/otherai/tools/n8n/)

[Dify教程](https://docs.whatai.cc/docs/otherai/tools/dify/)