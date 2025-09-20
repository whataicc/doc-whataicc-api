---
weight: 1
bookFlatSection: true
title: "Claude code 配置方式"

summary: "本页详细介绍神马中转API的功能、使用方法以及中转API服务的优势，帮助您快速上手并提升效率。"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---
# Claude code 配置方式

Claude Code 是 Anthropic 官方推出的命令行工具，为开发者提供强大的 AI 辅助编程体验。支持智能代码生成、代码分析、调试助手等功能。

### **🚀 主要功能**

*   **智能代码生成** - 快速生成高质量代码

*   **代码分析** - 深度理解和分析代码结构

*   **调试助手** - 智能发现和修复代码问题

*   **文档生成** - 自动生成代码文档

*   **命令行集成** - 无缝集成到开发流程

### ⭐**本站专属功能**

本站所有LLM 模型均支持在 Claude code 中使用

如果 Claude code 无法修改调用模型，可参考教程 令牌 中，设置模型转发

### **📦 安装步骤**

#### Mac & Liunx 配置方式

#### **1. 安装 Node.js**

确保系统已安装 Node.js 18+ 版本

##### **安装 Homebrew (mac推荐)**

如果尚未安装 Homebrew：
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
#### **2. 安装 Node.js**

使用 Homebrew：
```
brew install node
```
#### **2. 安装 Claude Code**
```
npm install -g @anthropic-ai/claude-code
```
#### **3. 配置 API 密钥**

##### **获取 Auth Token (参考添加令牌文档**

###### **方法一：使用 Bash（推荐）**
```
echo 'export ANTHROPIC_AUTH_TOKEN="sk-xxx"' >> ~/.bash_profile echo 'export ANTHROPIC_BASE_URL="https://api.whatai.cc"' >> ~/.bash_profile source ~/.bash_profile
```
###### **方法二：使用 Zsh（如果使用 Oh My Zsh）**
```
echo 'export ANTHROPIC_AUTH_TOKEN="sk-xxx"' >> ~/.zshrc echo 'export ANTHROPIC_BASE_URL="https://api.whatai.cc"' >> ~/.zshrc source ~/.zshrc
```
**注意：** 永久设置后需要重启终端才能生效。

#### **4. 启动使用 Claude Code**
```
# 进入项目目录
cd your-project-folder

# 启动 Claude Code
claude
```
**首次启动后需要先进行主题的选择等操作：**

*   • 选择喜欢的主题（回车）

*   • 确认安全须知（回车）

*   • 使用默认 Terminal 配置（回车）

*   • 信任工作目录（回车）

*   • 开始编程！🚀

#### Windows配置方式

1、**管理员权限**启动cmd

#### **1. 安装 Node.js**

访问  Node.JS 官网，点击最新版本，选择对应的操作系统和版本下载即可

下载后双击安装，之后一直点击下一步。安装完成后，打开 CMD 窗口，执行命令验证安装：
```
node -v
```
2、设置 npm 配置,告诉 npm 在安装包时忽略执行包中的脚本（如 preinstall、postinstall 等）,设置完重新启动CMD
```
setx NPM_CONFIG_IGNORE_SCRIPTS true
```
3、安装 Claude Code
```
npm install -g @anthropic-ai/claude-code
```
4、配置 SHELL 环境变量

###### **方法一：图形化配置（推荐，永久生效）**

a. 右键点击 "此电脑" → 选择 "属性"

b. 点击 "高级系统设置"

c. 在 "系统属性" 窗口中点击 "环境变量"

重要：在 "系统变量" 部分点击 "新建"（多人共享电脑可选择 "用户变量"）

d. 添加以下两个变量：

变量名：ANTHROPIC_AUTH_TOKEN，变量值：sk-xxx

变量名：ANTHROPIC_BASE_URL，变量值：https://api.whatai.cc

e. 点击 "确定" 保存

###### **方法二：PowerShell（永久设置）**


```PowerShell
[Environment]::SetEnvironmentVariable("ANTHROPIC_AUTH_TOKEN", "sk-xxx", "User")
[Environment]::SetEnvironmentVariable("ANTHROPIC_BASE_URL", "https://api.whatai.cc", "User")
```
###### **方法三：命令提示符（永久设置）**

CMD
```
setx ANTHROPIC_AUTH_TOKEN "sk-xxx"
setx ANTHROPIC_BASE_URL "https://api.whatai.cc"
```
**注意：** 永久设置后需要重启终端才能生效。推荐使用永久配置方式。

###### **方法四：通过**settings.json 设置

找到 settings.json 文件，如果没有请创建
```
C:\Users\{user}\.claude\settings.json
```
设置 API 信息，保存
```
{
    "env": {
      "ANTHROPIC_MODEL": "claude-sonnet-4-20250514",
      "ANTHROPIC_SMALL_FAST_MODEL": "claude-sonnet-4-20250514",
      "ANTHROPIC_BASE_URL": "https://api.whatai.cc",
      "ANTHROPIC_AUTH_TOKEN": "sk-AG2"
    }
  }
```
```
setx SHELL "C:\Program Files\Git\bin\bash.exe" #这里要换成你的路径， 
# 如果不知道，可以执行 where git 找一下 
```



5、添加 npm 环境变量

```
C:\Users\y.xie\.npm-global # 添加Windows环境变量，同样要设置为你的路径，在npm安装包里面
# 如果不知道，可以执行 npm config get prefix 找一下

```

将其添加到 Windows 的环境变量（PATH），关闭并重新打开你的终端窗口（CMD / PowerShell / Git Bash），使设置生效。

6、设置API配置

7、重启开发环境

8、enjoy!!

```
# 进入项目目录
cd your-project-folder

# 启动 Claude Code
claude
```

### **🎯 常用命令**

*   `claude` - 启动交互模式

*   `claude "task"` - 运行一次性任务

*   `claude commit` - 创建 Git 提交

*   `/help` - 显示可用命令

*   `/clear` - 清除对话历史

*   `/review` - 请求代码审查

### **💡 使用示例**

```
# 代码生成
> 请帮我写一个 Python 函数，用于计算斐波那契数列

# 代码审查
claude "review this code for potential bugs"

# 自动提交
claude commit

```

### **切换模型**

使用 Claude Code 命令：
```
/model [model id]
```
默认模型为`Sonnet 4`，你可以用效果更好的`Opus 4`：

**opus**
```
/model opus
```
或者，换成其他 claude 模型：

**sonnet 3.7**

**sonnet 3.5**
```
/model claude-3-7-sonnet-20250219
```
**Kimi K2 支持**启动 Claude Code 之后，只需要运行指令
```
/model moonshotai/kimi-k2-instruct
```
其他 LLM 模型均支持使用，比如 Openai、Gemini、Qwen、Doubao

### **⚠️ 重要提示**

1.   **API 密钥配置**：请将 `sk-your-api-key` 替换为您在 本站 生成的实际 API 密钥

2.   **令牌分组**：在 本站 创建令牌时，建议选择 "企业分组 官转分组"

3.   **网络连接**：确保网络连接稳定，工具需要与 API 服务器通信

4.   **项目目录**：建议在具体项目目录下使用，以获得更好的上下文理解

### **🔧 高级功能**

*   **IDE 集成** - 支持 Cursor 等 IDE 集成

*   **MCP 服务器** - 扩展 Agent 能力

*   **CI/CD 集成** - 自动化代码审查流程

*   **团队规范** - 通过CLAUDE.md文件定义团队规范
