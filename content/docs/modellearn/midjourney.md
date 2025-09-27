---
weight: 7
bookFlatSection: true
title: "Midjourney使用教程"

seo_title: "Midjourney使用教程_如何使用Midjourney中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# Midjourney使用教程 ​
----------------

> Midjourney（简称mj）和Niji-journey（简称niji）模式相同，都以mj举例

✨ 支持Midjourney官方所有功能

*   同时支持, Midjourney Proxy Plus, 以及, Midjourney Proxy 接口协议

*   如果你的项目不支持以上方式，请, 查看API接入文档, ，实现调用接口

*   适用性广，支持 Midjourney 所有操作

## 一、MJ Proxy Plus 快捷接入方式 ​
------------------------

Midjourney Proxy 主机： https://api.whatai.cc

Midjourney Proxy Secret：在令牌页生成的令牌，格式为 sk-xxxxxx 

![Image 1](https://pic2.imgdd.cc/item/68d618728dc72b176e6fce0f.png)

#### 不同的客户端需要填写不同的 BASE_URL ，请尝试以下地址： ​

*   https://api.whatai.cc

*   https://api.whatai.cc/mj

*   https://api.whatai.cc/mj/

*   https://api.whatai.cc/mj/submit/imagine

#### mode 参数（可选）： ​

*   relax, ：慢速（1-10分钟出图）

*   fast, ：快速（默认）（1-5分钟出图）

*   turbo, ：极速（1分钟内出图）

#### proxy-type 参数（可选）： ​

*   origin, ：图片使用 Discord 原地址，国外访问快，国内可能无法访问

*   relay, ：图片使用服务转发地址，全球访问快（默认）

*   proxy, ：图片使用管理员设置的地址，国内访问快（令牌可设置自己的图片代理地址）

## 二、切换绘图模式、图片代理 ​
---------------

#### 设置参数介绍： ​

*   fast, 是 Midjourney 的 fast mode（快速绘图模式），通常 1-5分钟内完成绘图

*   turbo, 是 Midjourney 的 turbo mode（极速绘图模式），通常 1分钟内完成绘图

*   relax, 是 Midjourney 的 relax mode（慢速绘图模式），通常 1-20分钟内完成绘图

*   relay, 是使用中转站地址转发，图片国内访问较快

*   origin, 是使用 Discord 原地址，图片国外访问快，国内不可访问

*   proxy, 是使用图片代理地址，替换, https://cdn.discordapp.com, 的地址，图片国内访问较快

设置优先级

令牌 > 路径参数 > 系统默认

### 1️⃣ 通过令牌管理控制（推荐） ​

> 在  ，选择要使用的令牌，点击编辑，设置想要管理的设置。

*   切换绘图模式方式，调整绘图速度 
![Image 2](https://pic2.imgdd.cc/item/68d618f68dc72b176e6fce35.png)

*   设置返回图片地址，方便国内访问（可使用自己的图片代理）

> *   在令牌编辑页设置自己的图片代理地址
> 
> *   PS: →, 自建图片代理教程, ，需要自备海外服务器，最好是国内线路优化、带宽大的

### 2️⃣ 通过URL路径参数 ​

*   切换绘图模式方式，调整绘图速度, 
*   /mj 默认是 fast 
*   mode/mj-fast/mj 是 fast 
*   mode/mj-turbo/mj 是 turbo 
*   mode/mj-relax/mj 是 relax 
*   mode示例：https://api.whatai.cc/mj-turbo/mj/submit/imagine 填写到程序中时，一般为：https://api.whatai.cc/mj-turbo
*   切换返回图片地址格式, /mj 是管理员设置的默认方式/mj-relay/mj 
*   使用服务转发地址，图片国内访问较快/mj-origin/mj 使用 Discord 原地址，图片国外访问快/mj-proxy/mj 使用管理员设置的代理地址，图片国内访问较快示例：https://api.whatai.cc/mj-relay/mj/submit/imagine 填写到程序中时，一般为：https://api.whatai.cc/mj-relay

同时支持多个参数

*   格式为：/mj-{mode}-{image_proxy}

*   示例： https://api.whatai.cc/mj-turbo-origin，采用【极速模式】，返回【Discord 原地址】。https://api.whatai.cc/mj-relax，采用【慢速模式】，返回【服务转发地址（默认）】。https://api.whatai.cc，采用【快速模式（默认）】，返回【服务转发地址（默认）】。

## 三、New API/Chat API/Shell API 接入MJ ​
-----------------------------------

*   渠道类型无所谓，只需渠道模型里有 Midjourney

*   配置代理地址为：https://api.whatai.cc

*   填写密钥为令牌页生成的令牌


## 四、Midjourney 价格表 ​
------------------

*   计费价格请参考, 模型价格页面的Midjourney栏 ：https://api.whatai.cc/models?provider=Mid-journey

*   类型 1 端点 ：价格随绘图模式（Fast/Relax/Turbo）变化

*   类型 2 端点 ：价格固定不变

*   类型 3 端点：免费端点，主要用于查询、继续完成任务

#### 类型 1 端点包括： ​

| 属性 | 解释 |
| --- | --- |
| Outpaint | 变焦 |
| Pan | 焦点移动 |
| Blend | 混图 |
| Inpaint | 局部重绘 |
| Upscale 2x | 放大2倍 |
| Upscale 4x | 放大4倍 |
| PicReader | 图生文后生成图片 |
| Reroll | 重新生成 |

#### 类型 2 端点包括： ​

| 属性 | 解释 |
| --- | --- |
| Upscale | 放大 |
| Describe | 图生文 |
| PicReaderRetry | 图生文重新生成 |
| FaceSwap | 换脸 |
| Shorten | Prompt 分析 |

#### 类型 3 端点包括： ​

| 属性 | 解释 |
| --- | --- |
| Fetch | 获取单个任务进度 |
| ListByIDs | 批量获取任务 |
| Modal | 确认提交弹窗任务 |
| Seed | 获取 Seed |
