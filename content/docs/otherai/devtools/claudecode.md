---
weight: 1
bookFlatSection: true
title: "Claude Code安装与国内使用教程"

seo_title: "「2025最新推荐」Claude Code国内使用_保姆级新手安装使用教程_神马中转API Claude Code代理API_最强AI编程工具"
summary: "Claude Code国内使用_Claude Code安装使用教程_神马中转API Claude Code代理API"
description: "Claude Code国内使用_Claude Code安装使用教程_神马中转API Claude Code代理API"
keywords: ["Claude Code国内使用","神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---
# 「2025最新推荐」Claude Code国内使用_保姆级新手安装使用教程_神马中转API Claude Code代理API_最强AI编程工具

## 什么是 Claude Code

Claude Code 是 Anthropic 推出的一个 agentic 编码工具 (agentic coding tool)，可以在命令行（terminal）中运行，或者集成在一些支持终端的 IDE 中，借助 Claude 的语言模型能力来辅助写代码、重构、调试、维护、理解代码库等。

![Claude Code国内使用_Claude Code安装使用教程_神马中转API Claude Code代理API](https://pic2.imgdd.cc/item/68d35e898dc72b176e6d5085.jpg)

### **Claude Code特点**

	•	能理解整个代码库的上下文，不只是单个文件； 

	•	支持自然语言命令 —— 用 “说”的方式让它做事情，比如 “帮我重构这个函数”、“让这个模块更高效”、“在这个地方加测试” 等； 

	•	可以执行命令／运行 shell 或 bash 命令并把输出作为上下文之一； 

	•	支持项目记忆（persistent project context），比如通过 CLAUDE.md 文件提供项目的风格、结构、常用脚本等，这样 Claude 在后续操作里就能“记得”这些规则。


### **🚀 主要功能**

*   **智能代码生成** - 快速生成高质量代码

*   **代码分析** - 深度理解和分析代码结构

*   **调试助手** - 智能发现和修复代码问题

*   **文档生成** - 自动生成代码文档

*   **命令行集成** - 无缝集成到开发流程

## ⭐**神马中转API专属功能**

神马中转API（api.whatai.cc）所有LLM 模型均支持在 Claude code 中使用

如果 Claude code 无法修改调用模型，可参考教程令牌中，设置模型转发


![Claude Code国内使用_Claude Code安装使用教程_神马中转API Claude Code代理API](https://pic2.imgdd.cc/item/68d35f358dc72b176e6d52d7.jpg)

## **📦 安装步骤**

### Mac & Liunx 配置方式

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

### Windows配置方式

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

## Claude Code 能做什么：功能列表

下面是 Claude Code 在实际开发中能帮你做的事情，列出来比较全，也分几类：

| 类别 | 功能 |
|---|---|
|代码生成 | 新建模块/组件/API/数据库模型 |
|重构优化 | 改变量名、优化性能、清理废代码 |
|调试修复 | 定位 bug、写单元测试、解决依赖冲突 |
|文档注释 | 自动生成 docstring / README / 使用指南 |
|跨语言转换 | Python ↔ JS / Go / Java 等 |
|代码审查 | 检查安全性、性能、风格一致性 |
|脚本任务 | 执行测试、构建、生成脚手架、CI/CD 配置 |
|理解项目 | 帮助快速熟悉陌生/遗留代码库 |


---

# Claude Code 实用教程：高效开发技巧与最佳实践

## 一、快速项目初始化与脚手架生成

### 1.1 创建全栈应用脚手架

#### 使用场景
需要快速搭建一个包含前后端的完整项目结构，包括配置文件、Docker支持、测试框架等。

#### 操作步骤

```bash
# 在终端中打开目标目录，然后启动 Claude
claude
```

#### Prompt 示例

```
请帮我创建一个全栈应用的项目结构，要求：
1. 后端：Node.js + Express + TypeScript + Prisma ORM
2. 前端：React + TypeScript + Vite + TailwindCSS
3. 包含 Docker Compose 配置（前端、后端、PostgreSQL、Redis）
4. 包含 ESLint、Prettier 配置
5. 包含 GitHub Actions CI/CD 配置
6. 包含完整的 README.md

项目名称：task-manager
请生成完整的目录结构和所有必要的配置文件。
```

#### 预期输出结构

```
task-manager/
├── backend/
│   ├── src/
│   │   ├── controllers/
│   │   ├── middlewares/
│   │   ├── models/
│   │   ├── routes/
│   │   ├── services/
│   │   ├── utils/
│   │   └── index.ts
│   ├── prisma/
│   │   └── schema.prisma
│   ├── tests/
│   ├── .env.example
│   ├── Dockerfile
│   ├── package.json
│   └── tsconfig.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── pages/
│   │   ├── services/
│   │   ├── utils/
│   │   ├── App.tsx
│   │   └── main.tsx
│   ├── Dockerfile
│   ├── package.json
│   ├── vite.config.ts
│   └── tsconfig.json
├── docker-compose.yml
├── .github/
│   └── workflows/
│       └── ci.yml
├── .gitignore
└── README.md
```

### 1.2 生成 API 端点与文档

#### Prompt 示例

```
基于以下数据模型，生成完整的 RESTful API：

模型：
- User (id, email, name, role, createdAt, updatedAt)
- Task (id, title, description, status, priority, assigneeId, createdAt, updatedAt)
- Comment (id, taskId, userId, content, createdAt)

要求：
1. 为每个模型生成完整的 CRUD 端点
2. 包含身份验证中间件（JWT）
3. 包含输入验证（使用 Joi 或 Zod）
4. 包含分页、排序、过滤功能
5. 生成 OpenAPI/Swagger 文档
6. 包含示例请求和响应

输出格式：完整的 routes 文件和 controller 文件
```

---

## 二、智能代码重构与优化

### 2.1 性能优化分析

#### 使用场景
发现代码性能问题，需要 Claude 分析并提供优化方案。

#### Prompt 示例

```
分析以下 React 组件的性能问题并提供优化方案：

[粘贴你的代码]

请从以下角度分析：
1. 不必要的重渲染
2. 内存泄漏风险
3. 大列表渲染优化
4. 异步操作优化
5. Bundle size 优化

输出：
- 问题清单（按严重程度排序）
- 每个问题的具体优化方案
- 优化后的完整代码
- 性能提升预期
```

### 2.2 代码现代化升级

#### Prompt 示例

```
将以下 JavaScript 代码升级为现代 TypeScript，要求：
1. 添加完整的类型定义
2. 使用 ES6+ 特性（async/await、解构、模板字符串等）
3. 改进错误处理
4. 添加 JSDoc 注释
5. 遵循 TypeScript 最佳实践

[粘贴旧代码]

额外要求：
- 保持向后兼容
- 列出所有破坏性变更
- 提供迁移指南
```

---

## 三、测试代码生成与覆盖率提升

### 3.1 生成完整测试套件

#### Prompt 示例

```
为以下模块生成完整的测试套件：

[粘贴你的代码模块]

测试要求：
1. 单元测试（Jest/Vitest）
2. 集成测试
3. 边界条件测试
4. 错误场景测试
5. Mock 外部依赖
6. 测试覆盖率目标：>90%

输出：
- 完整的测试文件
- 测试用例说明表格
- Mock 数据生成函数
- 测试运行配置
```

### 3.2 E2E 测试脚本生成

#### Prompt 示例

```
基于以下用户流程生成 Playwright E2E 测试：

用户流程：
1. 用户访问登录页
2. 输入邮箱和密码
3. 点击登录
4. 跳转到仪表板
5. 创建新任务
6. 编辑任务状态
7. 删除任务
8. 登出

要求：
- 使用 Page Object Model
- 包含断言验证
- 处理异步操作
- 添加截图功能
- 支持多浏览器测试
```

---

## 四、数据库操作与迁移

### 4.1 数据库 Schema 设计与优化

#### Prompt 示例

```
设计一个电商系统的数据库 schema，要求：

业务需求：
- 用户管理（多角色）
- 商品管理（多分类、多规格）
- 订单系统（状态流转）
- 库存管理（实时更新）
- 支付记录
- 评价系统

技术要求：
1. 使用 PostgreSQL
2. 考虑索引优化
3. 考虑数据分区
4. 包含触发器和存储过程
5. 生成 Prisma schema
6. 生成 SQL 迁移脚本
7. 包含种子数据脚本

输出格式：
- ER 图描述
- SQL DDL 语句
- Prisma schema
- 索引优化建议
```

### 4.2 数据迁移脚本生成

#### Prompt 示例

```
生成数据迁移脚本，将 MongoDB 数据迁移到 PostgreSQL：

MongoDB 集合结构：
{
  users: { _id, email, profile: { name, avatar }, posts: [postIds] },
  posts: { _id, userId, title, content, tags: [], comments: [{}] }
}

目标 PostgreSQL 结构：
- users 表
- profiles 表（1对1）
- posts 表
- tags 表
- post_tags 关联表
- comments 表

要求：
1. 处理数据类型转换
2. 处理关联关系
3. 包含回滚脚本
4. 批量处理大数据量
5. 错误处理和日志
6. 进度显示
```

---

## 五、API 集成与调试

### 5.1 生成 API 客户端

#### Prompt 示例

```
基于以下 OpenAPI 规范生成 TypeScript API 客户端：

[粘贴 OpenAPI JSON/YAML]

要求：
1. 完整的类型定义
2. 支持请求拦截器
3. 自动重试机制
4. 错误处理封装
5. 支持取消请求
6. 缓存机制
7. 生成使用示例

技术栈：Axios + TypeScript
```

### 5.2 Mock Server 生成

#### Prompt 示例

```
基于以下 API 规范创建 Mock Server：

API 列表：
- GET /api/users（分页）
- GET /api/users/:id
- POST /api/users
- PUT /api/users/:id
- DELETE /api/users/:id
- GET /api/users/:id/posts

要求：
1. 使用 Express + Faker.js
2. 支持动态数据生成
3. 模拟延迟和错误
4. 支持 WebSocket
5. 数据持久化（JSON 文件）
6. 支持场景切换
7. 包含 Docker 配置
```

---

## 六、调试与问题定位

### 6.1 错误分析与修复

#### Prompt 示例

```
分析以下错误并提供解决方案：

错误信息：
[粘贴完整的错误堆栈]

相关代码：
[粘贴相关代码片段]

环境信息：
- Node.js version: 18.x
- Framework: Next.js 14
- Database: PostgreSQL 15

要求：
1. 解释错误原因
2. 提供多种解决方案
3. 推荐最佳方案
4. 提供修复后的代码
5. 如何避免类似问题
```

### 6.2 性能问题诊断

#### Prompt 示例

```
诊断以下性能问题：

症状：
- API 响应时间从 100ms 增加到 2s
- 数据库查询缓慢
- 内存使用持续增长

提供的信息：
[慢查询日志]
[相关代码]
[性能监控数据]

请提供：
1. 问题根因分析
2. 优化方案（短期/长期）
3. 具体代码修改
4. 性能监控建议
5. 预防措施
```

---

## 七、文档生成与维护

### 7.1 生成项目文档

#### Prompt 示例

```
为项目生成完整文档：

项目结构：
[粘贴项目树形结构]

要求生成：
1. README.md（项目介绍、快速开始、架构说明）
2. API 文档（端点说明、请求示例、响应格式）
3. 部署文档（环境要求、部署步骤、配置说明）
4. 开发指南（代码规范、提交规范、分支策略）
5. 故障排查指南

格式要求：
- Markdown 格式
- 包含目录
- 包含示例代码
- 包含架构图（Mermaid）
```

### 7.2 代码注释生成

#### Prompt 示例

```
为以下代码添加详细注释：

[粘贴代码]

注释要求：
1. JSDoc/TSDoc 格式
2. 函数说明（目的、参数、返回值、异常）
3. 复杂逻辑说明
4. 算法时间/空间复杂度
5. 使用示例
6. 注意事项
7. TODO 和 FIXME 标记
```

---

## 八、CI/CD 配置生成

### 8.1 GitHub Actions 工作流

#### Prompt 示例

```
生成 GitHub Actions CI/CD 配置：

项目信息：
- 前端：React + TypeScript
- 后端：Node.js + TypeScript
- 数据库：PostgreSQL
- 部署目标：AWS ECS

要求：
1. PR 检查（lint、test、build）
2. 主分支自动部署到 staging
3. Tag 触发生产部署
4. 包含密钥管理
5. 并行执行优化
6. 缓存优化
7. 通知机制（Slack）

生成：
- .github/workflows/ci.yml
- .github/workflows/deploy.yml
- 部署脚本
```

---

## 九、代码审查与安全扫描

### 9.1 安全漏洞扫描

#### Prompt 示例

```
对以下代码进行安全审查：

[粘贴代码]

检查项：
1. SQL 注入
2. XSS 攻击
3. CSRF 攻击
4. 敏感信息泄露
5. 不安全的依赖
6. 权限验证漏洞
7. 加密问题
8. 输入验证

输出：
- 漏洞列表（按严重等级）
- 修复方案
- 修复后的代码
- 安全最佳实践建议
```



