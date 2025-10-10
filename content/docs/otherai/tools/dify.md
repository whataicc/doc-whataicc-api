---
weight: 3
bookFlatSection: true
title: "Dify教程"

seo_title: "【2025最新】Dify部署和工作流教程，国内直连OpenAI、Claude等配置Dify使用教程"
description: "了解神马中转API的使用方法，掌握如何配置和调用中转API服务，轻松解决接口调用难题。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务"]
tags: ["API", "中转API", "服务使用"]
categories: ["技术教程", "API文档"]

author: "神马中转API（api.whatai.cc）"
---

![【2025最新】Dify部署和工作流教程，国内直连OpenAI、Claude等配置Dify使用教程](https://pic2.imgdd.cc/item/68e8c4f08dc72b176e7f5fae.jpg)

Dify 是一款开源的大语言模型（LLM）应用开发平台。它融合了后端即服务（Backend as Service）和 LLMOps 的理念，使开发者可以快速搭建生产级的生成式 AI 应用。即使你是非技术人员，也能参与到 AI 应用的定义和数据运营过程中。

由于 Dify 内置了构建 LLM 应用所需的关键技术栈，包括对数百个模型的支持、直观的 Prompt 编排界面、高质量的 RAG 引擎、稳健的 Agent 框架、灵活的工作流，并同时提供了一套易用的界面和 API。这为开发者节省了许多重复造轮子的时间，使其可以专注在创新和业务需求上。

 

## 一、为什么使用 Dify？

你或许可以把 LangChain 这类的开发库（Library）想象为有着锤子、钉子的工具箱。与之相比，Dify 提供了更接近生产需要的完整方案，Dify 好比是一套脚手架，并且经过了精良的工程设计和软件测试。 重要的是，Dify 是**开源**的，它由一个专业的全职团队和社区共同打造。你可以基于任何模型自部署类似 Assistants API 和 GPTs 的能力，在灵活和安全的基础上，同时保持对数据的完全控制。

* * *

## **二、你能用 Dify 做什么**

+   快速搭建问答机器人（基于企业文档的 RAG）
    
+   构建会调用工具（搜索、调用 API、生成图片等）的 Agent（自动化任务）
    
+   在可视化画布上用“节点 + 触发 + 条件”编排复杂流程（Workflow）
    
+   通过 REST API 将这些能力嵌入现有业务系统（后端代理调用）
    
    （上面功能点与细节可在官方产品文档与代码库查看）。
    

![【2025最新】Dify部署和工作流教程，国内直连OpenAI、Claude等配置Dify使用教程](https://pic2.imgdd.cc/item/68e8c54c8dc72b176e7f63d7.png)

* * *

## **三、准备工作（最小环境 & 工具）**

+   最低硬件（参考仓库说明）：**CPU ≥ 2 core，RAM ≥ 4 GiB**（用于快速试验）。生产部署请按负载规划。
    
+   软件：Docker、Docker Compose（本教程以 Docker Compose 快速启动为例）；如果要生产部署可使用 Helm / Kubernetes。
    

* * *

## **四、快速入门 — 本地（Docker Compose）部署（最短命令）**

```
# 克隆仓库并启动（在支持 Docker 的机器上）
git clone https://github.com/langgenius/dify.git
cd dify/docker
cp .env.example .env   # 编辑 .env（填写管理员邮箱、数据库/MinIO/模型供应商的凭证等）
docker compose up -d
# 启动后到 http://localhost/install 进行初始化
```

> 上述为官方 quick start 的核心命令；具体 .env 字段和更高级部署（K8s/Helm/Terraform/AWS/CDK）见官方文档与仓库说明。

**注意**

+   .env.example 里会列出诸如数据库、存储（MinIO）、SMTP、初始管理员账号等变量，生产环境请使用安全凭证并放到安全 Vault。
    

* * *

## **五、核心概念与流程（快速理解）**

1.  **Model Provider（模型供应商）**：Dify 支持大量供应商（OpenAI、Anthropic、Azure OpenAI、Gemini、Hugging Face、Mistral、Replicate、Ollama、LocalAI 等），可以把外部模型或自部署模型接入到平台并供应用调用。
    
2.  **Knowledge（知识库 / RAG）**：把文档/PDF/网页/数据库转成可检索的向量/片段，查询时先检索相关片段再交给 LLM 生成，减少“幻觉”。
    
3.  **Workflow / Agent**：Workflow 是显式的节点流程（可视化编排），Agent 则是“策略驱动”的智能体（例如 Function Calling / ReAct），可动态选择并调用工具。
    
4.  **LLMOps / 监控**：Dify 提供日志、metric 与标注能力，便于持续优化 prompts、模型与数据。
    


## 六、使用神马中转API（国内直连）


#### 1.使用OpenAI模型

  点击右上角自己的头像，点击设置 

  ![Image 12](https://pic2.imgdd.cc/item/68cd0337fcdff65483031291.png)   

点击模型供应商，选择OpenAI的设置 

  ![Image 14](https://pic2.imgdd.cc/item/68cd0351fcdff654830312b1.png) 

  输入神马中转API 后台-使用API-API Keys 生成的API KEY，输入API Base：`https://api.whatai.cc/v1/chat/completions`，点击保存即可   

不同的版本尝试填入不同的API地址： `https://api.whatai.cc` `https://api.whatai.cc/v1` `https://api.whatai.cc/v1/chat/completions`  


 ![](https://pic2.imgdd.cc/item/68e8be1e8dc72b176e7f0972.png)

#### 2\. 使用其他模型

* * *

下拉找到OpenAI-API-compatible，选择添加模型 

  ![Image 20](https://pic2.imgdd.cc/item/68cd03ecfcdff654830313a8.png) 

  模型名称填写你想要使用的模型，准确的名称可以通过 模型价格页面 查看 输入神马中转AI 后台-使用API-API Keys 生成的API KEY，输入API Base：`https://api.whatai.cc/v1/chat/completions`，点击保存即可 

不同的版本尝试填入不同的API地址： `https://api.whatai.cc` `https://api.whatai.cc/v1` `https://api.whatai.cc/v1/chat/completions`  

 ![](https://pic2.imgdd.cc/item/68e8c19e8dc72b176e7f2717.png)  

* * *

## **七、构建知识库 (RAG) — UI 与 API 示例**

### **用 UI （最快）**

+   Dashboard -> Knowledge -> 创建知识库 -> 上传文件 / 粘贴文本 -> 选择索引策略（例如 high\_quality / economical 等） -> 触发索引。
    

### **用 API（适合自动化 / 批量）**

示例：通过文本创建文档（curl）：

```
curl --location --request POST 'https://api.dify.ai/v1/datasets/{dataset_id}/document/create_by_text' \
  --header 'Authorization: Bearer {api_key}' \
  --header 'Content-Type: application/json' \
  --data-raw '{"name": "company_faq","text": "这是一个关于产品的常见问题集合...","indexing_technique": "high_quality","process_rule": {"mode": "automatic"}}'
```

上传文件示例（curl）：（先上传文件或直接用 create\_by\_file）

```
curl --location --request POST 'https://api.dify.ai/v1/datasets/{dataset_id}/document/create_by_file' \
  --header 'Authorization: Bearer {api_key}' \
  --form 'data="{\"indexing_technique\":\"high_quality\",\"process_rule\":{\"mode\":\"custom\"}}";type=text/plain' \
  --form 'file=@"/path/to/file.pdf"'
```

（更多 API 列表、分段/元数据管理、查询接口参见知识库 API 文档页面）

* * *

## **八、在 Workflow / Agent 里使用知识检索（典型流程）**

1.  在 Workflow 画布放置 **知识检索（Knowledge Retrieval）** 节点，配置要检索的知识库与检索参数（top-k、元数据过滤等）。
    
2.  将知识检索节点的输出作为 LLM 节点的上下文输入（LLM 节点接收到用户 query + 检索到的片段）。
    
3.  如果需要自动化任务（如：查询网站、调用计算工具、生成图片等），使用 **Agent 节点** 并为其配置 Agent 策略（Function Calling / ReAct）与所需的 **Tools（工具）**。Dify 提供大量内置工具（搜索、图片生成、计算、外部 API 等），也支持导入 OpenAPI/Plugin 格式的自定义工具。
    

* * *

## **九、发布应用并通过 API 调用（示例）**

**获取 API Key 与发布**：在应用 -> 访问 API 页面生成访问凭据（注意安全。API Key 请只放后端使用，不要写在前端）。

**示例：调用聊天接口（curl）**

```
curl --location --request POST 'https://api.dify.ai/v1/chat-messages' \
  --header 'Authorization: Bearer ENTER-YOUR-SECRET-KEY' \
  --header 'Content-Type: application/json' \
  --data-raw '{
    "inputs": {},
    "query": "请帮我总结一下我上传的产品文档里关于退款政策的要点。",
    "response_mode": "streaming",
    "conversation_id": "your-conv-id",
    "user": "user-123"
  }'
```

**Python 示例（requests）**

```
import requests
url = "https://api.dify.ai/v1/chat-messages"
headers = {"Authorization": "Bearer YOUR_API_KEY", "Content-Type": "application/json"}
data = {
  "inputs": {},
  "query": "请列出产品 A 的主要功能",
  "response_mode": "sync"
}
r = requests.post(url, headers=headers, json=data)
print(r.status_code, r.json())
```

官方 API 文档有更多 endpoint（completion-messages、chat-messages、工作流调用、文件上传等）与示例。

* * *

## **十、进阶：自定义插件 / 新模型 / 工具**

+   **自定义工具**（OpenAPI / OpenAI plugin）：在 Tools -> 自定义，创建可供 Agent 调用的外部服务（例如内部 CRM API）。
    
+   **新增模型供应商 / 插件**：使用 Dify 的插件脚手架可以开发 model/provider 插件（需要 Python 环境，参见插件开发文档）。这允许把厂内自研推理服务接入 Dify。
    

* * *

## **十一、常见问题与排错技巧（实用）**

+   **启动后无法访问 /install**：检查 Docker container 是否运行，查看 docker compose ps，并查看容器日志 docker compose logs -f。
    
+   **API 请求示例缺少 base URL 导致 404/错误**：文档中的部分 curl 片段可能只给出相对路径，调用前请加上完整的 Base URL（例如 h ttp://localhost/v1/... 或 h ttps://api.dify.ai/v1/...）。有开发者因此报过相关问题。
    
+   **App unavailable / 400**：确保 App 已正确初始化、配置了模型供应商并启用了相应功能；在社区 issue 有类似错误的排查建议。
    

* * *

## **十二、完整示例：从零创建一个 RAG 问答机器人（快速脚本）**

1.  部署 Dify（参考第 4 节）。
    
2.  在 Dashboard -> Knowledge -> 新建知识库（或用 API 创建 POST /v1/datasets）。
    
3.  用 API 上传文档（示例见第 7 节的 create\_by\_file）。
    
4.  在 Workflow 画布：加入 **知识检索节点**（指向上面的知识库）→ **LLM 节点**（选择已配置的模型）→ 将检索结果拼接进 prompt。
    
5.  本地测试并调整 prompt 与检索 top-k，确认正确后发布应用并生成 API key。
