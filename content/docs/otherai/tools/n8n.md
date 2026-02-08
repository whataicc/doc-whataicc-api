---
weight: 4
bookFlatSection: true
title: "n8n教程"

seo_title: "【2025最新】n8n配置神马中转API，国内直连OpenAI、Claude等配置n8n使用教程"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---
# 【超详细】N8N教程：通过神马中转API稳定调用各大模型

**n8n**是一个开源（source-available）的**工作流程自动化平台**，它融合了“无代码/低代码”与“可编写代码扩展”的特点，让个人和技术团队都能创建复杂的自动化流程。

核心理念是让用户通过直观的“节点（Node）”串联来自动执行任务，而不是手动重复操作。它既可以自托管（部署到自己的服务器），也可以使用官方云服务。

![](https://pic.imgdd.cc/item/698475b0cb5013b47d1b1893.webp)

***

## **n8n主要特色与功能**

**1. 可视化工作流编辑器**

n8n 提供图形化拖拽编辑界面，用户可以像搭积木一样把“触发器 → 函数节点 → 应用集成 → 条件逻辑”连接成自动化流程。无需写大量程序，就能构建复杂逻辑。

***

**2. 超过 400+ 原生集成**

支持与大量常见服务和应用程序直接对接，例如 **GitHub、Google Sheets、Notion、Slack、数据库、Webhook 等**。通过这些集成节点，可以轻松完成数据同步、消息推送、事件触发等自动化操作。

***

**3. 代码灵活性强**

当可视化方案无法满足需求时，n8n 允许你在节点内编写自定义 JavaScript 或者 Python 代码，也可以安装 npm 包扩展功能，使自动化流程具有更强的逻辑能力。

***

**4. 原生 AI 支持**

n8n 平台本身已开始整合大量 AI 能力，可以将各种 AI 模型（如 LLM/Chat API）融入工作流，实现智能分析、文本生成、分类与推荐等功能。

***

**5. 自托管 & 完全控制**

不同于许多 SaaS 自动化工具，n8n 支持**完全自托管部署**，你可以在自己的服务器/容器中运行，这样保证数据安全、灵活调度和可审计性。也可选择官方云托管方案。

***

** 企业级功能**

除社区版之外，n8n 还提供企业级功能，例如访问权限管理、SSO（单点登录）、增强安全部署等，可以满足公司级规模自动化需求。

***

**活跃社区与模板库**

n8n 拥有强大的开发者和用户社区，提供大量现成工作流程模板，可以快速复制/修改使用，大大降低自动化上手门槛。

***

## **n8n核心优势**

| **维度** | **n8n 特点**           |
| ------ | -------------------- |
| 自由度    | 无代码拖拽 + 可写代码         |
| 扩展性    | 支持自定义节点、嵌入 JS/Python |
| 集成能力   | 400+ 内建应用节点          |
| 部署方式   | 云端 & 自托管             |
| 数据控制   | 使用者完全掌控              |
| AI 支持  | 原生 AI 工作流能力          |
| 社区资源   | 大量模板与教程              |

## n8n是什么

n8n 是一款兼具“可视化自动化”与“可扩展开发能力”的工作流程自动化平台，适合从非技术用户到高级开发者使用。通过它你可以把日常重复任务转成自动运行的流程，同时还能保持对执行逻辑和数据的完全掌控。 ![](https://pic.imgdd.cc/item/698475c1cb5013b47d1b18b1.png)

***

## n8n配置教程

### **在n8n新建工作流（Workflow）**

1.进入 n8n → **New Workflow******

![](https://pic.imgdd.cc/item/69847270cb5013b47d1b1774.png)

2.添加触发器：选择**手动触发**

![](https://pic.imgdd.cc/item/698472bfcb5013b47d1b177d.png)  

***

### **添加 OpenAI 节点并选择「Message a model」**

 

点击 “+” 添加下一个节点，搜索并选择 **OpenAI******

  ![](https://pic.imgdd.cc/item/6984731dcb5013b47d1b178c.png)  

在 OpenAI 节点的动作/操作里，选择 **Message a model**

  ![](https://pic.imgdd.cc/item/69847347cb5013b47d1b178d.png)

***

### **配置OpenAI Credentials**

在 OpenAI 节点里找到 Credentials（凭据）相关设置：

1. **创建新的 OpenAI Credential******

![](https://pic.imgdd.cc/item/698473e6cb5013b47d1b1793.png)

1. 填写：

   * **API Key**：粘贴你在神马中转后台生成的 Key，格式是：`sk-xxxxxx`

   * **Base URL**：填 `https://api.whatai.cc/v1`

2. 点 **Save** 保存

3. 保存后如果提示连接成功/可用，就说明通了。

![](https://pic.imgdd.cc/item/698473c8cb5013b47d1b1792.png)

***

### **配置一次最小可跑通的对话参数**

在 **OpenAI → Message a model** 节点里，通常需要这些字段：

* **Model**：填你要调用的模型名（在平台“支持模型”列表里找对应名称）

* **Messages / Prompt**：

  * role：user

  * content：例如 你好，给我一句 20 字以内的自我介绍。

然后点击 **Execute step** 测试运行。

***

## **常见报错排查**

* **401 Unauthorized**：API Key 贴错 / Key 没权限 / 没加 Bearer 前缀（HTTP Request 情况下最常见）。

* **404 Not Found**：BaseURL 多写/少写了 /v1，或你把 URL 写成了 .../v1/v1/...；中转常见可用形态包括 https\://api.whatai.cc、https\://api.whatai.cc/v1 等，但你当前要用的是 /v1 这一层，要确保拼接后路径正确。

* **model not found**：模型名不在支持列表里，去平台“支持模型”里复制正确的模型字段再填。
