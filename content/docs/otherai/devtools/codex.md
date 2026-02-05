---
weight: 6
bookFlatSection: true
title: "CodeX配置教程"

seo_title: "CodeX配置第三方神马中转API，AI编程工具Codex详细攻略"
summary: "CodeX国内使用_CodeX安装使用教程_神马中转API CodeX代理API"
description: "CodeX配置第三方神马中转API，AI编程工具Codex详细攻略"
keywords: ["CodeX国内使用","神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---


# CodeX配置第三方神马中转API，AI编程工具Codex详细攻略

在现代软件开发中，**代码规模越来越大、技术栈越来越复杂**，开发者花在“理解代码、改动代码、反复验证”的时间，往往远多于真正写新功能的时间。为了解决这一问题，**Codex** 应运而生。

**Codex（Codex CLI）** 是一个运行在终端中的 AI 编程助手。与普通聊天式 AI 不同，它可以直接读取你的项目代码、理解文件结构，在你的确认下修改源码、执行命令，并一步步完成真实的开发任务。你可以把它理解为一个“懂代码、会动手、但始终受你控制的编程搭档”。

![](https://pic.imgdd.cc/item/69831a01d9c88c98816d0632.webp)

在本文中，你将从零开始学习 Codex 的**安装、配置与实际使用方法**，包括如何接入第三方 API、如何在终端和 VS Code 中高效使用，以及遇到常见问题时如何快速排查。即使你从未使用过类似工具，也可以按照本文一步步完成配置，并真正把 Codex 用到你的日常开发中。

***

## **安装前准备（所有系统通用）**

* **Node.js 22+**

* **npm 10+**

* 稳定网络连接

> Windows 额外注意：OpenAI 官方也提到 Windows 支持偏“实验性”，更稳的方式是用 WSL 环境；

***

## **安装 Codex CLI**

### **Windows**

1. 安装 **Git Bash**（按安装向导一直下一步即可）。

2. 安装 Node.js（建议装最新 LTS）。

3. 安装 Codex CLI（在 CMD / PowerShell 里执行）：

```
npm install -g @openai/codex
```

4. 验证：

```
codex --version
```

### **macOS**

```
npm install -g @openai/codex
codex --version
```

必要时加 sudo。

OpenAI 官方也提供了 Homebrew 安装方式（可选）：brew install codex。

### **Linux**

1）先装 Node.js / npm（不同发行版命令不同）。

2）安装与验证：

```
sudo npm install -g @openai/codex
codex --version
```

***

## **配置神马中转API作为第三方API**

Codex CLI 会读取你的配置文件：一般在 \~/.codex/（Windows 也是用户目录下的 .codex）。创建两份文件：

* auth.json：放密钥

* config.toml：放模型与网关配置

### **Windows 配置路径与文件**

1）进入用户目录的 .codex（示例：C:\Users\testuser\\.codex）。如果看不到，先在资源管理器开启“显示隐藏项目”。

![](https://pic.imgdd.cc/item/69831685d9c88c98816d0434.png)

2）没有就手动创建 .codex 文件夹，并创建：

* auth.json

* config.toml

![](https://pic.imgdd.cc/item/69831ac3d9c88c98816d088e.png)

**auth.json（把 sk-xxx 换成你的神马中转API Key）**

```
{"OPENAI_API_KEY": "sk-xxx"}
```

**config.toml**

```

model_provider = "whatai"
model = "gpt-5-codex"
model_reasoning_effort = "high"
disable_response_storage = true
preferred_auth_method = "apikey"

[model_providers.whatai]
name = "whatai"
base_url = "https://api.whatai.cc/v1"
wire_api = "responses"
```

### **macOS / Linux 配置命令**

创建文件：

```
mkdir -p ~/.codex
touch ~/.codex/auth.json
touch ~/.codex/config.toml
```

编辑 auth.json（粘贴同样的 JSON）与 config.toml。**要保证上下一致**：model\_provider = "xxx" 要和 \[model\_providers.xxx] 的段名一致。

### **配置改完一定要“重启终端”**

**关闭终端/重启终端后再启动 codex**，让配置生效。

   

***

## **启动与基本使用（终端）**

进入你的项目目录：

```
cd your-project-folder
codex
```

你也可以直接在命令后跟一个初始任务，例如让它先解释仓库结构：

```
codex "Explain this codebase to me"
```

![](https://pic.imgdd.cc/item/69831a5ed9c88c98816d0670.png)  

### **推荐的使用习惯（很实用）**

* **先让它“读项目、给计划”**：比如“先扫描项目结构，列出你会修改哪些文件，再开始动手”。

* **小步提交**：每次只让它做一件事（修一个 bug / 加一个功能点）。

* **用 Git 做检查点**：Codex 会改文件，OpenAI 官方建议任务前后做 git checkpoint，方便回滚。

***

## **交互技巧：Slash 命令与快捷操作**

在 Codex 交互界面里，输入 / 可以打开 slash 命令菜单，用来切换模型、调整权限、总结对话等。

一些常见命令（示例来源于体验分享与官方说明思路一致）：

* /status：查看当前会话配置/状态

* /new：开新会话（清空上下文）

* /model：切换模型

* /init：初始化一些模板/设置（视版本而定）

另外，很多版本支持用 ! 直接跑终端命令（例如 !git status / !ls），能减少你“让模型代跑命令”的成本。

***

## **VS Code插件Codex**

流程是：**完成上述 .codex 配置后**，在 VS Code 扩展商店搜索并安装 codex，安装后会出现在侧边栏。

OpenAI 官方 quickstart 也提到：安装后 Codex 面板会出现在侧边栏（有时在折叠区）。

![](https://pic.imgdd.cc/item/698317aad9c88c98816d04bb.png)

***

## **常见问题（FAQ）与排查清单**

### **Q1：****codex: command not found ****/ 找不到命令**

**原因常见是 npm 全局安装路径没加入 PATH**，或安装没成功。

* 先运行 codex --version 验证是否安装成功。

* 重新安装：npm install -g @openai/codex

### **Q2：Linux/macOS 安装时报权限错误（EACCES）**

用 sudo npm install -g @openai/codex（Linux 写法）。

（更长期的做法是把 npm 全局目录改到用户目录，但这属于通用 Node/npm 运维，不是 Codex 专属。）

### **Q3：Windows 找不到 ****.codex****文件夹**

提醒：需要在资源管理器里打开“显示隐藏的项目”，因为 .codex 是隐藏目录风格。

### **Q4：配置了 Key 但仍提示未认证 / 401**

确认两点：

1）auth.json 内容必须是：

```
{"OPENAI_API_KEY": "sk-xxx"}
```

2）**重启终端**后再运行 codex。

### **Q5：一直连不上 / 超时 / 网络错误**

* 检查 base\_url 是否完全一致

* 公司/校园网络可能需要代理或放行相关域名（这是网络环境问题，不是 Codex 本身）。

### **Q6：模型不可用 / 报 model not found**

先用提供的模型名：gpt-5.2-codex。

如果你在神马中转API模型列表看到的名称不同，就要以实际可用模型为准（模型名不匹配会直接失败）。

### **Q7：****config.toml****写了但好像没生效**

最常见原因：

* model\_provider = "X" 和 \[model\_providers.X] **名字不一致**（比如一个写 whatai，另一个写 api111）。whatai的不同系统示例里名字确实不一样，所以你改的时候要保持一致。

* 忘记重启终端。

### **Q8：怎么升级 / 更新 Codex CLI？**

OpenAI 官方给的升级方式是：

```
npm i -g @openai/codex@latest
```

### **Q9：有哪些命令行参数/高级配置可以查？**

* 命令与 flag 参考：官方提供了“command line options”参考页，并说明 CLI 默认从 \~/.codex/config.toml 读取配置，也支持用 -c key=value 临时覆盖。

* 配置字段的完整参考：官方也有 config reference 页面。
