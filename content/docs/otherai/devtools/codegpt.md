---
weight: 3
bookFlatSection: true
title: "VSCode 插件 Code GPT 使用指南"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# VSCode 插件 Code GPT 使用指南
---

这个插件修改 Host 相对麻烦一些，需要修改源码才可以使用。以下是详细的步骤：

## 步骤 
----

![](https://pic.imgdb.cn/item/66da644cd9c307b7e9b2eea8.png")

这个插件修改Host相对麻烦一些，需要修改源码才可以使用。

1. 安装插件。安装好后按Ctrl+Shift+P，弹出框中输入Open Extensions Floder
![](https://pic.imgdb.cn/item/66da64f9d9c307b7e9b4b8f9.png)
1. 点击Extensions: Open Extensions Floder，这将打开插件目录，找到Code GPT的文件夹。
![](https://pic.imgdb.cn/item/66da650ed9c307b7e9b4c988.png)
1. 打开后进入打开文件./src/clients/openai_client.js，搜索文件中的api.openai.com，并替换为 `api.whatai.cc`。保存文件。
![](https://pic.imgdb.cn/item/66da652fd9c307b7e9b4e10d.png)
1. 再次回到vscode，按Ctrl+Shift+P，弹出框中输入CodeGPT: Set API KEY，点击CodeGPT: Set API KEY。然后将购买的Key输入进去即可。
![](https://pic.imgdb.cn/item/66da652fd9c307b7e9b4e10d.png)
1. 以上步骤完成后，重启VSCode

- 其他VSCode插件类似。