---
weight: 1
bookFlatSection: true
title: "Raycast插件ChatGPT使用指南（推荐使用）"

seo_title: "Raycast插件ChatGPT使用指南（推荐使用）_国内如何使用中转API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

# Raycast 插件 ChatGPT 使用指南（推荐使用）
---

Raycast 是一款高效的快捷启动与工作流管理工具，可以替代 Spotlight，更快地打开应用、执行脚本、调用 API、管理工作效率插件。它不仅适合开发者，也适合日常办公、学习场景。 

![Raycast安装教程与国内ChatGPT插件使用指南_MAC最强生产力软件_AI工具推荐](https://pic2.imgdd.cc/item/68d49fe88dc72b176e6e226f.png)


## **一、Raycast基础功能与特点**

**一、Raycast 基础功能**

1.  **应用启动**
    
    +   按 ⌘ + 空格 或自定义快捷键呼出 Raycast
        
    +   输入应用名称即可快速打开
        
2.  **文件与文件夹搜索**
    
    +   输入文件名、文件夹名即可快速定位
        
    +   支持预览、复制路径
        
3.  **系统控制**
    
    +   快速调整音量、亮度
        
    +   切换 Wi-Fi、蓝牙等
        
4.  **工作流与插件（Extensions）**
    
    +   Raycast 内置商店（Store）
        
    +   可以安装各类生产力工具（如 GitHub、Jira、Notion、ChatGPT 等插件）
        

![Raycast安装教程与国内ChatGPT插件使用指南_MAC最强生产力软件_AI工具推荐](https://pic2.imgdd.cc/item/68d49f948dc72b176e6e21da.png) **二、Raycast 的特点**

1.  **快速启动**：几乎零延迟的搜索和应用启动体验。
    
2.  **可扩展性强**：内置插件市场，开发者可以编写并分享自己的插件。
    
3.  **快捷命令**：支持自定义脚本（Shell、Python、JavaScript），快速执行。
    
4.  **工作流整合**：支持与 GitHub、Notion、Jira、Linear 等工具无缝结合。
    
5.  **美观 & 极简**：界面清爽、交互直观，键盘操作流畅无比。
    
6.  **免费为主**：核心功能免费，Pro 版提供团队协作和更强的个性化功能。
    

## **二、安装与配置 Raycast**

1.  **下载安装**
    
    +   官网：https://www.raycast.com
        
    +   支持 macOS
        
2.  **初始设置**
    
    +   设置全局快捷键（推荐：⌘ + 空格 替换 Spotlight）
        
    +   登录账号（方便同步插件和配置）
        
3.  **安装插件**
    
    +   打开 Raycast → 输入 Store → 搜索需要的插件 → 一键安装
        

 

## **三、插件推荐（高频实用🔥）**

以下推荐一些实用的 Raycast 插件，分为通用类和开发类：

### **🔧 通用效率类**

1.  **ChatGPT**
    
    +   直接在 Raycast 中调用 GPT 模型，快速生成文本、写代码、翻译。
        
2.  **Clipboard History**
    
    +   剪贴板管理神器，快速查找复制过的内容。
        
3.  **Emoji Search**
    
    +   通过关键字快速搜索 Emoji。
        
4.  **Google Translate**
    
    +   内置翻译功能，支持中英文互译。
        
5.  **Timer & Stopwatch**
    
    +   设置倒计时、专注时间。
        

### **💻 开发者类**

1.  **GitHub**
    
    +   查看 PR、Issue、仓库，快速跳转到网页。
        
2.  **Jira**
    
    +   管理任务、查看工单，适合团队协作。
        
3.  **Notion**
    
    +   快速搜索和打开页面。
        
4.  **Linear**
    
    +   管理任务，和敏捷开发结合良好。
        
5.  **Docker**
    
    +   查看容器状态，直接管理容器。
        

### **🌐 网络与工具类**

1.  **Google Search**
    
    +   快速搜索 Google 结果。
        
2.  **Currency Converter**
    
    +   实时汇率转换。
        
3.  **Weather**
    
    +   查看当前天气。
        
4.  **Raindrop.io**
    
    +   管理书签收藏。
        

## **四、Raycast 插件 ChatGPT 使用指南（重点 🔥）**

Raycast 的 ChatGPT 插件可以让你在任何场景下快速调用 GPT 能力，不需要额外切换到浏览器。

### **1\. 安装 ChatGPT 插件**

+   打开 Raycast → 输入 Store
    
+   搜索 **ChatGPT** 插件
    
+   点击 Install 安装
    

在 Raycast Store 中找到 ChatGPT 插件，并按照提示安装：

![Raycast插件ChatGPT使用指南](https://pic2.imgdd.cc/item/68d49ae28dc72b176e6e1fbc.png)

### **2\. API Key 配置**

ChatGPT 插件依赖 OpenAI API或者使用【神马中转API】，你需要：

1.  前往 OpenAI API Keys或者国内直连使用【神马中转API（api.whatai.cc）】
    
2.  复制 API Key
    
3.  打开 Raycast → 输入 ChatGPT → 设置 → 粘贴 API Key
    

安装完成后在该插件配置中的 `API Key` 中填入【神马中转API】的API Key，以及选中 `Change API Endpoint`，并在 `API Endpoint` 中填入 `https://api.whatai.cc/v1`

![Raycast插件ChatGPT使用指南](https://pic2.imgdd.cc/item/68d49b628dc72b176e6e1fc2.png) ![Raycast插件ChatGPT使用指南](https://pic2.imgdd.cc/item/68d49b848dc72b176e6e1fc7.png)  

### **3\. 快捷键设置**

+   你可以为 **ChatGPT 插件** 设置全局快捷键，比如：⌘ + ⇧ + G
    
+   随时唤出 ChatGPT，输入问题即可得到回答
    

### **4\. 使用场景**

+   **日常问答**：数学题、语法解释、编程调试
    
+   **文本处理**：中英文翻译、润色、写邮件
    
+   **开发辅助**：代码解释、生成正则、写脚本
    

🍺 enjoy it~ ![](https://pic.imgdb.cn/item/66da65dbd9c307b7e9b56670.gif)    

## **五、ChatGPT 插件使用示例**

以下是一些常见的使用场景示例：

### **示例 1：写代码**

```
用户输入：
用 Python 写一个快速排序

ChatGPT 输出：
def quick_sort(arr):
if len(arr) <= 1:
return arr
pivot = arr[len(arr)//2]
left = [x for x in arr if x < pivot]
middle = [x for x in arr if x == pivot]
right = [x for x in arr if x > pivot]
return quick_sort(left) + middle + quick_sort(right)

```

### **示例 2：文本润色**

```
用户输入：
请润色这句话 → “我很喜欢用raycast，因为它帮我提高效率”

ChatGPT 输出：
“我非常喜欢使用 Raycast，它极大地提升了我的工作效率。”
```

### **示例 3：快速学习**

```
用户输入：
请用简单的方式解释二叉树

ChatGPT 输出：
二叉树是一种数据结构，每个节点最多有两个子节点：左子树和右子树。就像一个家谱，每个人最多有两个孩子。
```

 

## **六、总结**

+   Raycast 是一个效率神器，结合插件可以替代大量工具
    
+   ChatGPT 插件让 AI 随时随地可用，提升学习、写作、编程效率
    
+   通过配置快捷键，你几乎可以把 ChatGPT 当成 **操作系统级别的助手**