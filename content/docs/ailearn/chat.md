# 基础教程-聊天 · 页面



**⚡ 双通道配置聊天** ​
---------------

⚠️ 请先创建令牌，才可使用站内聊天

**💻 管理入口****👉**[令牌控制台](https://api.whatai.cc/token)
📖**令牌配置指南**👉 基础知识-基本概念-添加令牌(填写项解析)



#### **🚀 方式一：闪电直连（推荐）**

> *   在令牌列表找到目标Key
> 
> *   点击「聊天」按钮
> 
> *   系统自动完成：
> 
> 
> - 注入Key到聊天窗
> 
> 
> - 配置BASE_URL
> 
> 
> - 选择默认模型

![Image 12](https://pic2.imgdd.cc/item/68cc0247fcdff6548301c089.png)


💡 适合场景：快速体验、临时调试

#### **🛠️ 方式二：手动配置（高级）**

**Step 1** 进入聊天页面 → 设置 ⚙️ → 服务端

**Step 2** 填写关键参数：
```
必备参数： 
API Key(令牌)  ███ sk-xxxxxxxxxxxx （粘贴复制的Key） 
BaseURL  ███ 选填以下任一：    
https://api.whatai.cc 
https://api.whatai.cc/v1    
https://api.whatai.cc/v1/chat/completions  

Midjourney专用地址：    
https://api.whatai.cc   
https://api.whatai.cc/mj

BaseURL指南：基础知识-基础概念-API地址（BaseURL）
```



**Step 3** 填写模型：

> 1. 访问「支持模型」页面
> 
> 
> 2. 复制目标模型名称（如 gpt-4-turbo）
> 
> 
> 3. 在聊天窗口粘贴到模型选择框
> 
> 
> 4.点击保存

![Image 16](https://pic2.imgdd.cc/item/68cc02d2fcdff6548301c0c5.png)

**Step 4** 回到聊天页面，可以开始聊天啦！！！！！！！