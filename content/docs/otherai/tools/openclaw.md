---
weight: 3
bookFlatSection: true
title: "OpenClaw配置教程"

seo_title: "【2026最新】OpenClaw配置神马中转API教程_OpenClaw推荐API"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

如果你已经开始折腾 **OpenClaw**，那你大概率很快会遇到一个现实问题：  
👉 **模型多、API 多、配置杂，越用越乱。**

这时候，强烈推荐你直接上 **神马中转API（api.whatai.cc）**，用它来配置 **OpenClaw**，真的会省掉一大半精力。

---

## 为什么用「神马中转API」来配 OpenClaw？

一句话总结：**少折腾、多稳定、好维护**。

- ✅ **统一入口**：不管你用的是哪家大模型，只需要在 OpenClaw 里配一次中转地址  
- ✅ **API Key 更清爽**：不用在 OpenClaw 里塞一堆厂商 Key，一个中转 Key 搞定  
- ✅ **切模型不改代码**：今天用 A，明天换 B，只改中转配置，不动 OpenClaw  
- ✅ **更适合长期运行**：对 Agent / Gateway 场景非常友好  

对 OpenClaw 这种「长期在线、持续调用模型」的 AI Agent 网关来说，中转 API 几乎是刚需。

---

## 用起来到底有多简单？

配置逻辑非常清晰：

1. 在 **神马中转API** 获取一个 API Key  
2. 在 OpenClaw 里把模型地址指向中转 API  
3. 统一通过中转调用各类大模型  

不需要关心不同厂商的参数差异，也不用反复改配置文件，**一次配置，长期省心**。

---

## 适合哪些人？

- 🧠 想认真玩 OpenClaw，而不是只跑 Demo  
- 🧩 同时接入多个模型 / 多个环境  
- 🔧 不想每次换模型都重新折腾配置  
- 🚀 想把 OpenClaw 稳定跑在本地或服务器上  

如果你希望 **OpenClaw 用起来像“基础设施”，而不是“实验项目”**，那中转 API 几乎是必选项。

[![nano-banana-2代理API中转推荐_神马中转API国内直连可试用稳定可靠的Gemini API中转站](https://pic2.imgdd.cc/item/68c78cabfcdff65483faea2a.jpg "神马聚合中转API_低价gpt_中转api_好用稳定的GPT代理_claude中转api_Midjourney代理_Suno代理_Luma代理")](https://api.whatai.cc)

很多人第一次用 AI，都会停留在“问答工具”这个阶段：帮你写点文案、改改代码、查查资料。但用着用着就会发现一个问题——**它很聪明，却什么也“做不了”**。

你还是得自己打开文件、复制内容、切换应用、执行命令，AI 更像一个“场外顾问”，而不是能真正帮你干活的助手。

如果你也想过：**有没有一种 AI，可以像真人助理一样，直接在我的电脑和工具里动手？******

那你很可能会对 **OpenClaw** 感兴趣。

![](https://pic.imgdd.cc/item/69a7beaaa9cdb1e92dcd106a.webp)

## **什么是OpenClaw**

**OpenClaw** 是一个开源、本地部署的 **AI 智能体网关**，它让你可以在自己的电脑或服务器上运行一个智能助手，通过聊天平台随时使用这个助手来完成任务。它的目标不是像普通聊天机器人那样只回答问题，而是能真正执行动作，例如访问本地文件、自动化任务或联动应用等，这些都是通过统一的 Gateway 网关实现的。

OpenClaw 原名 Clawdbot，因 Anthropic 商标顾虑在 2026年1月27日更名为 Moltbot（过渡名），最终在1月30日确定为 OpenClaw。三个名字本质是同一个项目，功能完全一致。

 

***

## **核心能力和特点**

OpenClaw 的设计强调实用性和扩展性，它包含一些核心能力：

* **本地部署与隐私控制**：在用户自己的机器上运行，你的数据不用上传到第三方服务器。

* **多平台接入**：支持通过各种消息平台（如 Telegram、Discord、企业微信、飞书、QQ 等）和智能体互动。

* **技能扩展系统**：通过“Skills（技能）”系统来扩展能力，例如文件管理、知识管理、自动化操作等。

* **工作原理由 Gateway 驱动**：Gateway 是核心组件，它负责消息路由、会话管理和不同平台的连接。

 

## OpenClaw安装

为了获得最佳体验，我们推荐：

**操作系统**：

* **Mac（强烈推荐）**：原生支持最完善，可操作日历、备忘录、截图等系统功能
* Windows：完全可用，但部分系统集成功能受限
* Linux：适合开发者，配置灵活

### Mac本地部署（推荐）

> **最佳体验**：如果你有Mac电脑，强烈推荐本地部署，体验最好、功能最全！

#### 系统要求

**硬件要求**：

* CPU：M系列芯片或Intel i5以上
* 内存：8GB以上（推荐16GB）
* 硬盘：10GB以上空闲空间

**系统版本**：

* macOS 12 Monterey 或更高版本
* 推荐 macOS 14 Sonoma 或 macOS 15 Sequoia

**前置软件**：

* Node.js 22.0.0+（会自动安装）
* Homebrew（可选，用于安装依赖）

 

#### 安装步骤

##### 第一步：打开终端

1. 按 `Command + 空格` 打开 Spotlight
2. 输入 `Terminal` 或`终端`
3. 按回车打开终端

![](https://pic.imgdd.cc/item/69a7c542a9cdb1e92dcd14b5.png)  

##### 第二步：安装 OpenClaw

在终端中执行以下命令：

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

安装过程会自动：

* 检测系统环境
* 安装Node.js（如果未安装）
* 下载OpenClaw
* 配置环境变量

**预计时间**：2-5分钟

##### 第三步：验证安装

安装完成后，执行以下命令验证：

```bash
openclaw --version
```

如果显示版本号（如 `2026.2.9`），说明安装成功！

##### 第四步：初始化配置

运行配置向导：

```bash
openclaw onboard
```

**配置流程**：

**1. 接受风险提示**：

选择 `Yes` 继续

![](https://pic.imgdd.cc/item/69a7c542a9cdb1e92dcd14b5.png)

**2. 选择启动模式**：

推荐选择 `QuickStart` 快速启动：

**3. 选择AI模型**：

选择你的AI供应商选择Custom Provider：

![](https://pic.imgdd.cc/item/69ae57ebb4a2eb58b526f991.png)  

**4. 输入BaseURL和API Key**：

输入模型BaseURL：`https://api.whatai.cc/v1`，输入对应的API Key，选择`OpenAI-compatible`，输入模型ID如：`claude-sonnet-4-6`

![](https://pic.imgdd.cc/item/69ae582bb4a2eb58b526fb6c.png)  
![](https://pic.imgdd.cc/item/69ae5878b4a2eb58b526fd76.png)  
![](https://pic.imgdd.cc/item/69ae58e8b4a2eb58b52700e7.png)  

**5. 选择聊天工具**：

* 如果要接入飞书/Telegram，选择对应选项
* 如果暂时不接入，选择 `None`（后续可配置）

![](https://pic.imgdd.cc/item/69a7c5a3a9cdb1e92dcd150c.png)

**6. Gateway端口设置**：

默认 `18789` 即可：

![](https://pic.imgdd.cc/item/69a7c5b5a9cdb1e92dcd1522.png)

**7. 选择Skills**：

使用空格键选择你需要的技能，也可以直接跳过：

![](https://pic.imgdd.cc/item/69a7c5c5a9cdb1e92dcd1533.png)

**8. API Key配置**：

没有的可以选择 `no` 跳过：

![](https://pic.imgdd.cc/item/69a7c5d2a9cdb1e92dcd153c.png)

**9. 启用Hooks**：

推荐启用这三个钩子（用于内容引导、日志和会话记录）：

![](https://pic.imgdd.cc/item/69a7c5dca9cdb1e92dcd1545.png)

**10. 完成配置**：

配置完成后，会自动启动Gateway服务并打开Web UI（`http://127.0.0.1:18789/chat`）

##### 第五步：验证安装

```bash
# 检查Gateway状态
openclaw channels status

# 应该显示：
# Gateway reachable.
```

### Windows本地部署

> 🪟 **Windows用户**：完全可用，但部分系统集成功能受限。

**硬件要求**：

* CPU：2核以上
* 内存：4GB以上（推荐8GB）
* 硬盘：10GB以上空闲空间

**操作系统**：

* Windows 10 或 Windows 11

**前置软件**：

* Node.js 22.0.0+
  
#### 部署方式选择

Windows有两种部署方式：

1. **WSL2 + Ubuntu（强烈推荐）**：官方推荐方式，提供完整Linux环境支持
2. **PowerShell原生部署**：纯Windows环境，适合不想使用WSL2的用户

#### 方式一：WSL2 + Ubuntu部署（强烈推荐）

这是官方推荐的Windows部署方式，提供最完整的Linux环境支持。

##### 第一步：启用WSL2

**以管理员身份打开PowerShell**，执行：

```powershell
# 启用WSL功能
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

# 设置WSL 2为默认版本
wsl --set-default-version 2
```
**重启计算机**。

##### 第二步：安装Ubuntu

**方法一：Microsoft Store安装（推荐）**

1. 打开Microsoft Store，本地商店或者网页：https://apps.microsoft.com/search?query=Ubuntu+22.04+LTS&hl=zh-CN&gl=CN
2. 搜索「Ubuntu 22.04 LTS」或「Ubuntu 24.04 LTS」
3. 点击「获取」并安装
4. 首次启动设置用户名和密码

安装完成后会自动打开Ubuntu终端，按提示设置用户名和密码。

![](https://pic.imgdd.cc/item/69ae24c8fe73d60a1df4c3b2.png)


##### 第三步：更新Ubuntu系统

在Ubuntu终端中执行：

```bash
# 更新软件包列表
sudo apt update && sudo apt upgrade -y

# 安装基础工具
sudo apt install -y curl git wget build-essential
```

![](https://pic.imgdd.cc/item/69ae2551fe73d60a1df4c632.png)

##### 第四步：安装Node.js 22+

```bash
#运行 NVM 安装脚本
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.1/install.sh | bash

#使 NVM 生效
source ~/.bashrc

#安装 Node.js：
nvm install 22

#验证 Node.js 版本（必须≥22.x）
node --version
npm --version
```
##### 第五步：安装 OpenClaw

**一键脚本安装**

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

![](https://pic.imgdd.cc/item/69ae2756fe73d60a1df4d941.png)

**选择AI模型**：

选择你的AI供应商选择Custom Provider：

![](https://pic.imgdd.cc/item/69ae57ebb4a2eb58b526f991.png)  

**输入BaseURL和API Key**：

输入模型BaseURL：`https://api.whatai.cc/v1`，输入对应的API Key，选择`OpenAI-compatible`，输入模型ID如：`claude-sonnet-4-6`

![](https://pic.imgdd.cc/item/69ae582bb4a2eb58b526fb6c.png)  
![](https://pic.imgdd.cc/item/69ae5878b4a2eb58b526fd76.png)  
![](https://pic.imgdd.cc/item/69ae58e8b4a2eb58b52700e7.png)  

##### 第六步：验证安装

```bash
# 查看版本
openclaw --version

# 查看帮助
openclaw --help

# 查看系统状态
openclaw status
```
##### 第七步：配置Windows访问WSL2服务

由于OpenClaw运行在WSL2中，需要配置端口转发以便Windows访问。

**创建启动脚本** `start-openclaw.bat`：

```batch
@echo off
echo Starting OpenClaw Gateway in WSL2...
wsl -d Ubuntu-22.04 -u root service openclaw start
timeout /t 3
start http://localhost:18789
```
或直接在WSL2中启动：

```bash
# 在WSL2 Ubuntu终端中
openclaw gateway run --port 18789
```
然后在Windows浏览器访问 `http://localhost:18789`

---




#### PowerShell原生部署(不推荐)

##### 第一步：安装Node.js 22+

**方法一：官网下载安装**

1. 访问 https\://nodejs.org/zh-cn
2. 下载Windows安装包（LTS版本22.x）
3. 运行安装程序，勾选「自动安装必要的工具」

##### 第二步：验证Node.js安装

```bash
# 打开PowerShell
node -v
npm -v
```

##### 第三步：以管理员身份安装 OpenClaw

**重要**：必须以**管理员身份**运行PowerShell。

```bash
# 安装最新稳定版
npm install -g openclaw@latest

# 或安装汉化版
npm install -g @qingchencloud/openclaw-zh@latest
```

##### 第四步：解决安装权限问题

如果遇到权限错误：

```bash
# 方法A：启用PowerShell脚本执行
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

# 方法B：修改npm安装目录
npm config set prefix "C:\npm"
npm config set cache "C:\npm-cache"

# 将目录添加到PATH
[Environment]::SetEnvironmentVariable("Path", $env:Path + ";C:\npm", "User")
```

##### 第五步：验证安装

```bash
openclaw --version
openclaw --help
```

##### 第六步：解决常见问题

**问题：sharp模块加载失败**

```bash
# 清理npm缓存
npm cache clean --force

# 重新安装
npm install -g openclaw@latest --force
```

**问题：Windows Defender阻止**

将OpenClaw安装目录添加到Windows Defender排除项：

```
C:\Users\你的用户名\AppData\Roaming\npm
C:\Users\你的用户名\.openclaw
```

***

##### 初始化配置

安装完成后，需要运行初始化向导。

启动初始化向导

```bash
openclaw onboard --install-daemon
```

***

### Linux本地部署

> **Linux用户**：适合开发者，配置灵活。

#### 系统要求

**推荐发行版**：

* Ubuntu 20.04+
* Debian 11+
* CentOS 8+

#### 安装步骤

##### 第一步：安装Node.js

```bash
# Ubuntu/Debian
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt-get install -y nodejs

# 验证安装
node --version
```

##### 第二步：安装 OpenClaw

```bash
curl -fsSL https://openclaw.ai/install.sh | bash
```

##### 第三步：验证安装

```bash
openclaw --version
```

##### 第四步：初始化配置

```bash
openclaw onboard
```

## OpenClaw配置神马中转API

下面介绍三种方法设置OpenClaw配置神马中转API

### 1.安装时直接设置

**选择AI模型**：

选择你的AI供应商选择Custom Provider：

![](https://pic.imgdd.cc/item/69ae57ebb4a2eb58b526f991.png)  

**4. 输入BaseURL和API Key**：

输入模型BaseURL：`https://api.whatai.cc/v1`，输入对应的API Key，选择`OpenAI-compatible`，输入模型ID如：`claude-sonnet-4-6`

![](https://pic.imgdd.cc/item/69ae582bb4a2eb58b526fb6c.png)  
![](https://pic.imgdd.cc/item/69ae5878b4a2eb58b526fd76.png)  
![](https://pic.imgdd.cc/item/69ae58e8b4a2eb58b52700e7.png)  

### 2.安装完毕可视化修改

启动openclaw之后左侧菜单【设置-配置】- Models - 输入模型BaseURL：`https://api.whatai.cc/v1`，输入对应的API Key，选择`OpenAI-compatible`，输入模型ID如：`claude-sonnet-4-6`

![](https://pic.imgdd.cc/item/69ae59beb4a2eb58b5270796.png)  


### 3.其他版本可修改配置文件

OpenClaw 的配置文件位置通常如下： **系统文件路径示例** 

Windows:`C:Users用户名.openclawopenclaw.json` 

macOS:`~/.openclaw/openclaw.json` 

Linux:`~/.openclaw/openclaw.json`  

需要手动编辑配置文件 `~/.openclaw/openclaw.json`，指定：

* `baseUrl`：API服务地址
* `apiKey`：认证密钥
* `api`：API协议类型（如 `openai-completions`、`anthropic-messages`）
* `models`：模型列表和参数

#### 配置神马中转API代理

如果你使用API代理服务，配置如下：

```json
{
  "models": {
    "mode": "merge",
    "providers": {
      "whataicc": {
        "baseUrl": "https://api.whatai.cc/v1",
        "apiKey": "sk-xxxxx-你的神马中转API密钥",
        "auth": "api-key",
        "api": "openai-completions",
        "models": [
          {
            "id": "claude-sonnet-4-6",
            "name": "claude-sonnet-4-6",
            "contextWindow": 200000,
            "maxTokens": 8192
          },
          {
            "id": "gpt-4",
            "name": "GPT-4",
            "contextWindow": 128000,
            "maxTokens": 4096
          }
        ]
      }
    }
  },
  "agents": {
    "defaults": {
      "model": {
        "primary": "whataicc/claude-sonnet-4-6"
      }
    }
  }
}
```

#### 配置参数说明

 

| 参数              | 说明      | 示例                                 |
| --------------- | ------- | ---------------------------------- |
| `baseUrl`       | API服务地址 | `https://api.whatai.cc`            |
| `apiKey`        | API 密钥  | `sk-xxx`                           |
| `auth`          | 认证方式    | `api-key` 或 `bearer`               |
| `api`           | API协议   | `openai-completions`、`anthropic-messages` |
| `id`            | 模型ID    | `deepseek-chat`                    |
| `name`          | 显示名称    | `DeepSeek Chat`                    |
| `contextWindow` | 上下文窗口   | `64000`                            |
| `maxTokens`     | 最大输出    | `4096`                             |

#### 常见API协议类型

 

* `openai-completions`：OpenAI兼容接口（最常用）
* `anthropic-messages`：Anthropic Claude接口
* `google-generative-ai`：Google Gemini接口

#### 配置后重启服务

 

```bash
# 方式1：重启Gateway
openclaw gateway restart

# 方式2：停止后重新启动
systemctl --user stop openclaw-gateway.service
systemctl --user start openclaw-gateway.service

# 方式3：完全重启
systemctl --user restart openclaw-gateway.service
```

#### 验证配置

 

```bash
# 查看当前配置的模型
openclaw models list

# 测试模型连接
openclaw models test whataicc/claude-sonnet-4-6
```

## 常见问题及解决方案

使用问题或配置问题查看，OpenClaw中文帮助文档：https://docs.openclaw.ai/zh-CN

### 问题1：找不到配置文件

**排查步骤**:

1. **检查配置文件是否存在**

   ```bash
   ls -la ~/.openclaw/openclaw.json
   ls -la ~/.openclaw/agents/*/openclaw.json
   ```

2. **运行 doctor 命令**

   ```bash
   openclaw doctor
   ```

3. **手动创建配置文件**

   ```bash
   mkdir -p ~/.openclaw
   echo '{}' > ~/.openclaw/openclaw.json
   ```

***

### 问题2：多个 Agent 配置混乱

**解决方案**:

1. **查看所有 Agent**

   ```bash
   openclaw agents list
   ```

2. **查看每个 Agent 的配置**

   ```bash
   openclaw config get --agent main-assistant
   openclaw config get --agent tech-dev
   ```

3. **统一管理**

   * 使用全局配置 + Agent 覆盖
   * 或者每个 Agent 完全独立配置

### **问题3：Node.js版本不对**

```bash
# 检查版本
node --version

# 如果低于22，升级
nvm install 22
nvm use 22
```

### **问题4：**** 权限错误**

```bash
# macOS/Linux
sudo chown -R $USER ~/.openclaw

# Windows
# 以管理员身份运行PowerShell
```

### 问题5：API配置问题

 

**API Key无效**

* 检查是否完整复制（包括sk-前缀）
* 检查是否有多余空格
* 检查账户余额是否充足

**模型不可用**

* 检查模型ID是否正确
* 检查API服务是否正常
* 尝试切换其他模型

**Token消耗太快**

* 使用更便宜的模型
* 优化提示词
* 定期清理会话历史

### 问题6：Gateway问题

 

**Q1: Gateway无法启动**

```bash
# 查看日志
tail -f ~/.openclaw/logs/gateway.log

# 重启Gateway
openclaw gateway restart
```

**Q2: 端口被占用**

```bash
# 查看端口占用
lsof -i :18789

# 修改端口
openclaw config set gateway.port 18790
```
