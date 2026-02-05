---
weight: 6
bookFlatSection: true
title: "VSCode插件Claude Code for VSCode配置神马中转APIAI详细设置与使用教程"

seo_title: "VSCode插件Claude Code for VSCode配置神马中转APIAI详细设置与使用教程"
summary: "Claude Code国内使用_Claude Code安装使用教程_神马中转API Claude Code代理API"
description: "VSCode插件Claude Code for VSCode配置神马中转APIAI详细设置与使用教程"
keywords: ["Claude Code国内使用","神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---
# VSCode插件Claude Code for VSCode配置神马中转APIAI详细设置与使用教程

在 VS Code 中使用 **Claude Code**，意味着你可以把大模型的编码能力真正“嵌入”到日常开发流程中，而不是停留在浏览器里来回复制代码。Claude Code for VSCode 是 Anthropic 官方推出的 VS Code 扩展，它为 Claude Code 提供了原生的图形化交互界面，能够直接在 IDE 内完成代码理解、修改、规划和审查，是目前在 VS Code 中使用 Claude Code 的**推荐方式**。

通过该扩展，你不仅可以像使用普通 AI 聊天工具一样向 Claude 提问，还可以让它**直接读取并理解当前项目的真实代码上下文**。扩展支持内联差异（Inline Diff）展示修改结果，在真正写入文件之前，你可以清晰地看到 Claude 打算做哪些改动；支持使用 @ 提及文件、文件夹，甚至精确到某个行号范围，让 Claude“只看你想让它看的代码”；同时还引入了“计划（Plan）”与“权限模式”的概念，在执行任何自动修改前先给出完整方案，由你确认后再动手，最大程度保证代码安全性和可控性。

![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982e22fd9c88c98816cb371.webp)

在本教程中，我们将从 **Claude Code for VSCode 的安装与基础使用** 开始，逐步讲清楚扩展的核心功能和使用方式；然后重点讲解国内用户和企业环境中最常见、也是最容易踩坑的部分——**如何配置“AI 中转 / 神马中转 API”**，包括不同登录与接入方案的区别、settings.json 的正确写法，以及常见问题的排查方法，帮助你在 VS Code 中稳定、顺畅地使用 Claude Code 完成真实开发任务。

 

***

## **安装Claude Code for VSCode**

1. VS Code 版本要求：**1.98.0+**。

2. 扩展安装：扩展商店搜索 **“Claude Code”** → 安装 → 必要时重启或 Developer: Reload Window。

3. 打开面板：编辑器右上角会出现 **Spark 图标**；也可以命令面板输入 “Claude Code” 打开。

![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982dd87d9c88c98816cb1be.png)

***

## **配置“神马中转API”**

实际有三种登录方式，本质就是要通过认证你才能使用，点击选项卡会提示你跳转到对应的说明文档，如下图所示： ![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982de37d9c88c98816cb1fa.png)   我们其实可以直接配置API KEY、BASE URL，比如接入神马中转API模型，点这个插件的设置（齿轮）进去，然后找到 在 settings.json 中编辑 点进去，如下图所示： BASE URL神马中转API官网：`https://api.whatai.cc` ![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982de19d9c88c98816cb1f1.png) 添加如下内容，**保存 settings.json 后**，先退出 VSCode，再重新进入。

```
{

"name": "ANTHROPIC_AUTH_TOKEN",

"value": "sk-xxxxxxx"

},

{

"name": "ANTHROPIC_BASE_URL",

"value": "https://api.whatai.cc"

},
```

![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982de85d9c88c98816cb220.png)   最后，**测试在 VSCode 中成功使用 Claude Code 插件**  

## 开始使用

安装后，您可以通过 VS Code 界面开始使用 Claude Code：  

### 1.打开 Claude Code 面板

在整个 VS Code 中，Spark 图标表示 Claude Code：Spark 图标 打开 Claude 的最快方式是点击编辑器工具栏（编辑器右上角）中的 Spark 图标。该图标仅在您打开文件时出现。 ![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982df91d9c88c98816cb268.png) 打开 Claude Code 的其他方式： 命令面板：Cmd+Shift+P（Mac）或 Ctrl+Shift+P（Windows/Linux），输入”Claude Code”，然后选择一个选项，如”在新选项卡中打开” 状态栏：点击窗口右下角的 ✱ Claude Code。即使没有打开文件也可以使用。 您可以拖动 Claude 面板在 VS Code 中重新定位。

### 2.发送提示

要求 Claude 帮助您处理代码或文件，无论是解释某些内容的工作原理、调试问题还是进行更改。

> Claude 会自动看到您选择的文本。按 Option+K（Mac）/ Alt+K（Windows/Linux）也可以在您的提示中插入 @-提及引用（如 @file.ts#5-10）。

以下是询问文件中特定行的示例： ![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982dffbd9c88c98816cb287.png)  

### 3.审查更改

当 Claude 想要编辑文件时，它会显示原始内容和建议更改的并排比较，然后请求许可。您可以接受、拒绝或告诉 Claude 改为做什么。 ![VSCode插件Claude Code for VSCode配置AI中转与详细使用教程](https://pic.imgdd.cc/item/6982e021d9c88c98816cb291.png) VS Code 显示 Claude 建议更改的差异，带有权限提示，询问是否进行编辑

## **Claude Code for VSCode 详细使用教程（高频功能）**

**打开与多会话**

* Spark 图标快速打开面板；也可命令面板打开。

* 支持“在新选项卡/新窗口打开”多会话并行处理任务。

**@ 引用文件/文件夹（让它“读代码”）**

* 输入 @ + 文件名/目录名可引用内容；支持模糊匹配。

* Option+K / Alt+K 可插入带行号范围的引用（如 @app.ts#5-10）。

**权限模式（强烈建议你先用 Plan）**

提示框底部可切换模式：

* default：每步操作都询问许可

* plan：先给计划，等你确认再动手

* acceptEdits / bypass：更激进（风险更高）

也可以在 VS Code 设置里用 claudeCode.initialPermissionMode 设默认值。

**Slash 命令菜单（/）**

在输入框里输入 / 打开命令菜单：附加文件、切模型、扩展思考、/usage 等。

**终端模式（CLI 风格）**

扩展默认是图形聊天面板；你可以在扩展设置里勾选 **useTerminal** 切到终端模式。

**扩展设置 vs Claude Code 设置：别配错地方**

官方区分得很清楚：

* **VS Code 扩展设置**：控制扩展在 VS Code 内的行为（如 disableLoginPrompt、useTerminal、initialPermissionMode 等）。

* **\~/.claude/settings.json**：扩展与 CLI 共享（环境变量、允许的命令、hooks、MCP servers、plugins 等）。

 

## 修复常见问题

### 扩展无法安装

确保您有兼容版本的 VS Code（1.98.0 或更高版本） 检查 VS Code 是否有权安装扩展 尝试从 VS Code Marketplace 直接安装  

### Spark 图标不可见

Spark 图标在您打开文件时出现在编辑器工具栏（编辑器右上角）中。如果您看不到它： 打开文件：该图标需要打开文件。仅打开文件夹是不够的。 检查 VS Code 版本：需要 1.98.0 或更高版本（帮助 → 关于） 重启 VS Code：从命令面板运行”Developer: Reload Window” 禁用冲突的扩展：临时禁用其他 AI 扩展（Cline、Continue 等） 检查工作区信任：扩展在受限模式下不工作 或者，点击状态栏（右下角）中的”✱ Claude Code”。即使没有打开文件也可以使用。您也可以使用命令面板（Cmd+Shift+P / Ctrl+Shift+P）并输入”Claude Code”。 ​

### Claude Code 从不响应

如果 Claude Code 没有响应您的提示： 检查您的互联网连接：确保您有稳定的互联网连接 开始新对话：尝试开始新对话以查看问题是否仍然存在 尝试 CLI：从终端运行 claude 以查看是否获得更详细的错误消息 如果问题仍然存在，请在 GitHub 上提交问题，并提供有关错误的详细信息。 ​

### 卸载扩展

要卸载 Claude Code 扩展： 打开扩展视图（Mac 上为 Cmd+Shift+X 或 Windows/Linux 上为 Ctrl+Shift+X） 搜索”Claude Code” 点击卸载 要也删除扩展数据并重置所有设置：

```
rm -rf ~/.vscode/globalStorage/anthropic.claude-code
```

 
