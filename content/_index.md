---
bookHeadingAnchor: false
layout: landing
title: "神马中转API一站式AI大模型API中转站 · 低价好用稳定的中转API服务"

summary: "神马聚合中转API是一个高效的Open AI、Midjourney API代理、Claude代理、Suno代理等供应商
我们致力于提供优质的 API 接入服务，让您可以轻松集成先进的AI模型至您的产品和服务。通过 API 综合管理平台，无缝整合OpenAl最尖端的人工智能模型。借助我们可靠且易于使用的API解决方案，升级您的产品与服务。"
description: "神马聚合中转API是一个高效的Open AI、Midjourney API代理、Claude代理、Suno代理等供应商
我们致力于提供优质的 API 接入服务，让您可以轻松集成先进的AI模型至您的产品和服务。通过 API 综合管理平台，无缝整合OpenAl最尖端的人工智能模型。借助我们可靠且易于使用的API解决方案，升级您的产品与服务。"
keywords: ["神马中转API", "如何使用中转API", "中转API服务","Claude API中转站","Claude国内中转站","ChatGPT中转API","OpenAI中转API","国内中转API","如何使用中转API"]
---

<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>AI中转站 - 一站式AI API服务平台</title>
  <style>
    *{margin:0;padding:0;box-sizing:border-box;}
    body{font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",Roboto,"Helvetica Neue",Arial,sans-serif;background:#0a0e27;color:#fff;overflow-x:hidden;}
    a{text-decoration:none;color:inherit;}

    /* 背景动画 */
    .bg-animation{position:fixed;top:0;left:0;width:100%;height:100%;background:linear-gradient(135deg,#667eea,#764ba2,#4facfe,#00f2fe);background-size:400% 400%;animation:gradientMove 15s ease infinite;z-index:-2;opacity:.15;}
    @keyframes gradientMove{0%{background-position:0% 50%;}50%{background-position:100% 50%;}100%{background-position:0% 50%;}}
    .particles{position:fixed;top:0;left:0;width:100%;height:100%;z-index:-1;}
    .particle{position:absolute;width:2px;height:2px;border-radius:50%;background:rgba(255,255,255,.6);animation:float 20s linear infinite;}
    @keyframes float{from{transform:translateY(100vh);opacity:0;}20%{opacity:1;}80%{opacity:1;}to{transform:translateY(-100vh);opacity:0;}}

    /* nav */
    nav{position:fixed;top:0;width:100%;padding:20px 40px;background:rgba(10,14,39,.6);backdrop-filter:blur(10px);z-index:1000;transition:.3s;}
    nav.scrolled{background:rgba(10,14,39,.95);padding:12px 40px;}
    .nav-container{max-width:1200px;margin:auto;display:flex;justify-content:space-between;align-items:center;}
    .logo{font-size:24px;font-weight:bold;background:linear-gradient(135deg,#667eea,#764ba2);-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
   .logo a {
      display: flex;
      align-items: center;
      font-size: 1.2rem; /* 你可以根据需要调整文字大小 */
      text-decoration: none;
      color: inherit;
    }

    .logo-img {
      height: 20px !important;
      width: auto;     /* 按比例缩放 */
      margin-right: 0.4em;
      vertical-align: middle;
    }
    .nav-links{display:flex;list-style:none;gap:20px;}
    .nav-links a:hover{color:#667eea;}

    /* hero */
    .hero{padding:140px 20px 100px;text-align:center;}
    .hero h1{font-size:3.5rem;margin-bottom:20px;background:linear-gradient(135deg,#667eea,#764ba2,#4facfe);background-size:200% 200%;-webkit-background-clip:text;-webkit-text-fill-color:transparent;animation:textGradient 6s linear infinite;}
    @keyframes textGradient{0%{background-position:0% 50%;}100%{background-position:100% 50%;}}
    .hero p{font-size:1.2rem;color:#aaa;max-width:600px;margin:0 auto 40px;}

    .btn{padding:14px 30px;border-radius:40px;font-weight:600;cursor:pointer;border:none;position:relative;overflow:hidden;}
    .btn-primary{background:linear-gradient(135deg,#667eea,#764ba2);color:#fff;}
    .btn-secondary{background:transparent;border:2px solid #667eea;color:#fff;}

    /* AI 输入框特效 + 呼吸光效 */
.ai-input-box{
    max-width:600px;
    margin:0 auto 40px;
    position:relative;
}
.ai-input{
    width:100%;
    padding:16px 20px;
    border-radius:40px;
    border:2px solid rgba(255,255,255,.2);
    background:rgba(255,255,255,.05);
    color:#fff;
    font-size:1.1rem;
    outline:none;
    box-shadow:0 0 10px rgba(102,126,234,0.2);
    transition:0.4s;
    animation: glowPulse 2s ease-in-out infinite alternate;
}
.ai-input:focus{
    border-color:#667eea;
    box-shadow:0 0 20px rgba(102,126,234,0.6);
}
@keyframes glowPulse{
    0%{box-shadow:0 0 5px rgba(102,126,234,0.2);}
    50%{box-shadow:0 0 20px rgba(102,126,234,0.6);}
    100%{box-shadow:0 0 10px rgba(102,126,234,0.3);}
}

.ai-cursor{
    position:absolute;
    top:50%;
    right:20px;
    transform:translateY(-50%);
    width:10px;
    height:24px;
    background:#fff;
    animation:blink 1s infinite;
}
@keyframes blink{0%,50%{opacity:1;}51%,100%{opacity:0;}}



    .cta-buttons{display:flex;justify-content:center;gap:15px;margin-bottom:40px;margin-top:50px;}
    .btn{padding:14px 30px;border-radius:40px;font-weight:600;cursor:pointer;border:none;position:relative;overflow:hidden;}
    .btn-primary{background:linear-gradient(135deg,#667eea,#764ba2);color:#fff;}
    .btn-secondary{background:transparent;border:2px solid #667eea;color:#fff;}
    /* section title */
    .section{padding:80px 20px;max-width:1200px;margin:auto;}
    .section-title{text-align:center;font-size:2.2rem;margin-bottom:10px;background:linear-gradient(135deg,#667eea,#764ba2);-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
    .section-subtitle{text-align:center;color:#aaa;margin-bottom:40px;}

    /* 核心优势 - 卡片 */
    .features-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(260px,1fr));gap:20px;}
    .feature-card{background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.1);border-radius:15px;padding:30px;transition:.3s;}
    .feature-card:hover{transform:translateY(-8px);background:rgba(255,255,255,.08);box-shadow:0 12px 24px rgba(102,126,234,.3);}

    /* 功能亮点 - 横向 */
    .highlights{display:flex;flex-wrap:wrap;gap:20px;justify-content:center;}
    .highlight-item{flex:1 1 250px;background:rgba(255,255,255,.05);padding:20px;border-radius:12px;text-align:center;}

    /* 应用场景 - 图片+描述 */
    .scenarios{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:30px;}
    .scenario{background:rgba(255,255,255,.05);border-radius:15px;overflow:hidden;}
    .scenario img{width:100%;height:200px;object-fit:cover;}
    .scenario div{padding:20px;}

    /* 我们的成绩 - 数字 */
    .stats{display:flex;flex-wrap:wrap;justify-content:center;gap:40px;}
    .stat-item{text-align:center;}
    .stat-number{font-size:2.5rem;font-weight:bold;background:linear-gradient(135deg,#667eea,#764ba2);-webkit-background-clip:text;-webkit-text-fill-color:transparent;}
    .stat-label{color:#aaa;}

    /* 主流模型支持 - logo展示 */
    .models{display:flex;flex-wrap:wrap;justify-content:center;gap:30px;}
    .model{background:rgba(255,255,255,.05);padding:20px 30px;border-radius:10px;font-weight:bold;}

    /* FAQ */
    .faq{max-width:800px;margin:auto;}
    .faq-item{margin-bottom:15px;border:1px solid rgba(255,255,255,.1);border-radius:10px;overflow:hidden;}
    .faq-question{padding:15px;background:rgba(255,255,255,.05);cursor:pointer;font-weight:bold;}
    .faq-answer{max-height:0;overflow:hidden;transition:max-height .3s ease;padding:0 15px;color:#aaa;}
    .faq-item.active .faq-answer{max-height:200px;padding:15px;}

    /* footer */
    footer{background:rgba(10,14,39,.95);padding:40px 20px;margin-top:60px;}
    .footer-container{max-width:1200px;margin:auto;display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:30px;}
    .footer-column h4{margin-bottom:15px;font-size:1.1rem;color:#fff;}
    .footer-column ul{list-style:none;}
    .footer-column li{margin-bottom:8px;color:#aaa;}
    .copyright{text-align:center;margin-top:20px;color:#777;font-size:.9rem;}




  </style>
</head>
<body>
  <div class="bg-animation"></div>
  <div class="particles" id="particles"></div>

  <!-- nav -->
  <nav id="navbar">
    <div class="nav-container">
      <div class="logo" style="font-size:40px">
        <a href="/">
          <img src="/favicon.png" alt="logo" class="logo-img" style="height:60px;vertical-align:bottom">
          神马中转API
        </a>
      </div>
      <ul class="nav-links">
  		  <li><a href="#achievements">我们的成绩</a></li>    
		    <li><a href="#models">模型支持</a></li>    
		    <li><a href="#core">核心优势</a></li>
        <li><a href="#highlights">功能亮点</a></li>
        <li><a href="#scenarios">应用场景</a></li>
        <li><a href="#faq">常见问题</a></li>
      </ul>
    </div>
  </nav>

  <!-- hero -->
  <section class="hero">
    <h1>神马中转API</h1>
    <p>一站式AI大模型API中转站 · 低价好用稳定的中转API服务</p>
    <!-- AI 输入框特效 -->
    <div class="ai-input-box">
      <div class="ai-input" id="aiInput">
        <span class="typed-text" id="typedText"></span>
        <span class="ai-cursor"></span>
      </div>
    </div>
    <div class="cta-buttons" style="margin-top:50px">
      <a href="https://api.whatai.cc" class="btn btn-primary" style="color:#FFFFFF">立即开始</a>
      <a href="/docs/introduction/" class="btn btn-secondary">查看文档</a>
    </div>
  </section>
  <!-- 我们的成绩 -->
  <section class="section" id="achievements">
    <h2 class="section-title">我们的成绩</h2>
    <div class="stats">
      <div class="stat-item"><div class="stat-number" data-target="600">0</div><div class="stat-label">接入模型</div></div>
      <div class="stat-item"><div class="stat-number" data-target="10000">0</div><div class="stat-label">日均请求量（万）</div></div>
      <div class="stat-item"><div class="stat-number" data-target="99.99">0</div><div class="stat-label">好评率%</div></div>
    </div>
  </section>

  <!-- 主流模型支持 -->
  <section class="section" id="models">
    <h2 class="section-title">主流模型支持</h2>
    <div class="models">
      <div class="model">
        <div class="model-category">
        <div class="model-header">
          <h3>OpenAI 顶级大模型</h3>
        </div>
        <div class="model-list">
          <div class="model-item featured">
            <span class="model-name">GPT-5</span>
            <span class="model-badge">最新</span>
          </div>
          <div class="model-item">
            <span class="model-name">GPT-4.1</span>
          </div>
          <div class="model-item">
            <span class="model-name">o1 & o3</span>
            <span class="model-badge">推理</span>
          </div>
          <div class="model-item">
            <span class="model-name">GPT-4o</span>
          </div>
          <div class="model-item">
            <span class="model-name">GPT-4o-mini</span>
          </div>
          <div class="model-item">
            <span class="model-name">Text-to-Image</span>
            <span class="model-badge">图像</span>
          </div>
          <div class="model-item">
            <span class="model-name">Text-to-Speech</span>
            <span class="model-badge">语音</span>
          </div>
          <div class="model-item">
            <span class="model-name">......</span>
          </div>
        </div>
      </div>    
      </div>
      <div class="model">
      <!-- Anthropic 系列 -->
      <div class="model-category">
        <div class="model-header">
          <h3>Anthropic AI大模型</h3>
        </div>
        <div class="model-list">
          <div class="model-item featured">
            <span class="model-name">Claude 4.1</span>
            <span class="model-badge">最新</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 4 Opus</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 4 Sonnet</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 3.7</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 3.5 Sonnet</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 3 Opus</span>
          </div>
          <div class="model-item">
            <span class="model-name">Claude 3 Haiku</span>
          </div>
          <div class="model-item">
            <span class="model-name">......</span>
          </div>          
        </div>
      </div>      
      </div>
      <div class="model">
 <div class="model-category">
        <div class="model-header">
          <h3>开源大模型</h3>
        </div>
        <div class="model-list">
          <div class="model-item featured">
            <span class="model-name">DeepSeek R1</span>
            <span class="model-badge">推理</span>
          </div>
          <div class="model-item">
            <span class="model-name">DeepSeek V3</span>
          </div>
          <div class="model-item">
            <span class="model-name">Kimi K2</span>
          </div>
          <div class="model-item">
            <span class="model-name">GLM-4.5</span>
          </div>
          <div class="model-item">
            <span class="model-name">Qwen3-Coder</span>
            <span class="model-badge">编程</span>
          </div>
          <div class="model-item">
            <span class="model-name">Qwen3-32B</span>
          </div>
          <div class="model-item">
            <span class="model-name">LongCat-Flash</span>
          </div>
          <div class="model-item">
            <span class="model-name">......</span>
          </div>          
        </div>
      </div>      
      </div>
    </div>
  </section>


  <!-- 核心优势 -->
  <section class="section" id="core">
    <h2 class="section-title">核心优势</h2>
    <div class="features-grid">
      <div class="feature-card"><h3>⚡ 极速响应</h3><p>多节点部署，智能调度，毫秒级响应</p></div>
      <div class="feature-card"><h3>🔒 最新支持</h3><p>即时同步全球最新AI大模型，确保您始终掌握最新技术</p></div>
      <div class="feature-card"><h3>💰 成本优化</h3><p>按需计费、多档价位、便宜实惠</p></div>
      <div class="feature-card"><h3>📈 高可用性</h3><p>99.9% SLA，7x24小时稳定运行</p></div>
    </div>
  </section>

  <!-- 功能亮点 -->
  <section class="section" id="highlights">
    <h2 class="section-title">功能亮点</h2>
    <div class="highlights">
      <div class="highlight-item">统一API接口</div>
      <div class="highlight-item">跨平台支持</div>
      <div class="highlight-item">智能路由分流</div>
      <div class="highlight-item">实时监控与统计</div>
    </div>
  </section>

  <!-- 应用场景 -->
  <section class="section" id="scenarios">
    <h2 class="section-title">应用场景</h2>
    <div class="scenarios">
      <div class="scenario">
        <img src="https://picsum.photos/600/400?random=1" alt="chatbot"/>
        <div><h3>智能客服</h3><p>利用大语言模型提供实时客户支持。</p></div>
      </div>
      <div class="scenario">
        <img src="https://picsum.photos/600/400?random=2" alt="content"/>
        <div><h3>内容创作</h3><p>文章、广告文案、脚本快速生成。</p></div>
      </div>
      <div class="scenario">
        <img src="https://picsum.photos/600/400?random=3" alt="analysis"/>
        <div><h3>数据分析</h3><p>自然语言查询和智能报表生成。</p></div>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section class="section" id="faq">
    <h2 class="section-title">常见问题</h2>
    <div class="faq">
      <div class="faq-item">
        <div class="faq-question">如何开始使用？</div>
        <div class="faq-answer">注册账号👉 <a href="https://api.whatai.cc" target="_blank">神马中转API首页</a>，获取API Key，即可调用接口。</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">支持哪些计费方式？</div>
        <div class="faq-answer">按需计费、按次计费、多档价位、便宜实惠</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">如何获取 Openai Key？ 如何获取 Claude Key？ 如何获取 gemini key？</div>
        <div class="faq-answer">💻 操作入口👉 <a href="https://api.whatai.cc/token" target="_blank">神马中转API令牌控制台</a>，Key就是令牌！这个key可以使用站内支持模型页面介绍的所有模型（260+），GPT系列模型、Claude系列模型、gemini系列模型等等等</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">单个key的并发或RPM、TPM有限制吗？</div>
        <div class="faq-answer">没有限制。神马中转API不会主动限制用户 RPM TPM ，但所有模型账号都是所有用户共享，遇到使用高峰可能会 429 或 500 报错。</div>
      </div>
      <div class="faq-item">
        <div class="faq-question">你们的服务是否兼容OpenAI接口协议？</div>
        <div class="faq-answer">我们的服务完全兼容OpenAI接口协议，支持无缝对接各种OpenAI接口应用。这意味着您可以轻松将我们的服务集成到现有系统中，无需担忧兼容性问题。</div>
      </div>   
      <div class="faq-item">
        <div class="faq-question">为什么 gpt-5 说自己是 gpt-4o 是正确的？而chatGPT官方回答自己是gpt-5？</div>
        <div class="faq-answer">这是新手常见误会。询问模型“你是谁”获得了不达预期的回答。这是因为模型在训练过程中是没有自己模型型号信息的，但包含了老模型的相关信息。模型厂商同时训练很多模型，某个模型达到某个设定效果后才会给模型命名，所以你问 gpt-5 是谁，他回答自己是 gpt-4o 。openai官方的chatgpt是成熟的网页端产品，在前端对此类问题做了优化，所以你问官方模型能回答自己是gpt-5。</div>
      </div>   
      <div class="faq-item">
        <div class="faq-question">常见错误以及解决办法</div>
        <div class="faq-answer">查看教程文档👉 <a href="/docs/errorcode/" target="_blank">神马中转API教程文档</a></div>
      </div>                          
    </div>
  </section>

  <!-- footer -->
  <footer>
    <div class="footer-container">
      <div class="footer-column">
        <h4>友情链接</h4>
        <ul><li><a href="https://whatai.cc" target="_blank">AI导航</a></li>
        <li><a href="https://api.whatai.cc" target="_blank">神马中转API官网</a></li>
        <li><a href="https://www.aihubproxy.com" target="_blank">AIHub智慧代理API</a></li>
        </ul>
      </div>
      <div class="footer-column">
        <h4>教程文章</h4>
        <ul>
        <li><a href="/docs/introduction/" target="_blank">AI中转站使用教程</a></li>
        <li><a href="/docs/otherai/chat/chatbox/" target="_blank">Chatbox教程</a></li>
         <li><a href="docs/otherai/tools/raycast/" target="_blank">Raycast教程</a></li>
        <li><a href="/docs/otherai/devtools/codegpt/" target="_blank">Code GPT教程</a></li>
        <li><a href="/docs/ailearn/wallet/" target="_blank">神马中转API使用教程</a></li>
        <li><a href="/docs/aidocs/base/" target="_blank">神马中转API基础知识</a></li>             
        </ul>
      </div>
    </div>
    <div class="copyright">© 2025 神马中转AI. 保留所有权利. ｜ <a href="/sitemap.xml" target="_blank">网站地图</a></div>
  </footer>

  <script>
    // 粒子
    function createParticles(){
      const container=document.getElementById('particles');
      for(let i=0;i<40;i++){
        const p=document.createElement('div');
        p.className='particle';
        p.style.left=Math.random()*100+'%';
        p.style.animationDuration=(15+Math.random()*10)+'s';
        p.style.animationDelay=(Math.random()*20)+'s';
        container.appendChild(p);
      }
    }

    // nav scroll
    window.addEventListener('scroll',()=>{document.getElementById('navbar').classList.toggle('scrolled',window.scrollY>50);});

    // 数字动画
    function animateNumbers(){
      document.querySelectorAll('.stat-number').forEach(num=>{
        let target=parseFloat(num.dataset.target);let count=0;let step=target/100;
        function update(){count+=step;if(count<target){num.textContent=Math.floor(count);requestAnimationFrame(update);}else{num.textContent=target;}}
        update();
      });
    }

    // FAQ
    document.addEventListener('click',e=>{
      if(e.target.classList.contains('faq-question')){e.target.parentElement.classList.toggle('active');}
    });
const slogans = [
  "一站式AI API服务平台，轻松接入GPT、Claude、Gemini等模型",
  "高性能AI中转，全球多节点，毫秒级响应",
  "智能路由，稳定可靠，保障99.9%服务可用性",
  "多模型统一接口，降低开发成本，提高效率",
  "实时监控与统计，让AI应用掌控全局"
];

const typedText = document.getElementById('typedText');
let currentSlogan = 0;

function typeSlogan() {
  typedText.textContent = '';
  const text = slogans[currentSlogan];
  let i = 0;

  function typeChar() {
    if (i < text.length) {
      typedText.textContent += text.charAt(i);
      i++;
      setTimeout(typeChar, 80);
    } else {
      setTimeout(() => {
        currentSlogan = (currentSlogan + 1) % slogans.length;
        typeSlogan();
      }, 2000);
    }
  }

  typeChar();
}

document.addEventListener('DOMContentLoaded', typeSlogan);
    document.addEventListener('DOMContentLoaded',()=>{createParticles();animateNumbers();});
  </script>
</body>
</html>