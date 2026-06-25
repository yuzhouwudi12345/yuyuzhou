<!-- 导航栏 -->
<nav>
    <div class="nav-container">
        <a href=" ">首页</a >
        <a href="#about">关于我</a >
        <a href="#skill">专业技能</a >
        <a href="#project">项目展示</a >
        <a href="#contact">联系方式</a >
    </div>
</nav>

<!-- 头部Banner -->
<section class="hero" id="home">
    <div class="hero-avatar">马</div>
    <h1>个人自我介绍</h1>
    <p>热爱前端开发｜专注网页设计｜积极进取的计算机学生</p >
</section>

<!-- 关于我 -->
<div class="wrap" id="about">
    <h2 class="title">关于我</h2>
    <p>我是马腾远一名计算机专业在读学生，在校期间系统学习了网页设计、前端开发、计算机基础等课程。我热爱网页制作，喜欢简约干净的设计风格。本个人网站为课程期末作业，采用原生HTML、CSS、JavaScript开发，无任何外部框架与资源依赖，结构清晰、适配移动端，具备完整的展示与交互功能。</p >
</div>

<!-- 技能进度条 -->
<div class="wrap" id="skill">
    <h2 class="title">专业技能</h2>

    <div class="skill">
        <div class="skill-top"><span>HTML 网页结构搭建</span><span>92%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar" data-width="92%"></div></div>
    </div>

    <div class="skill">
        <div class="skill-top"><span>CSS 样式布局美化</span><span>88%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar" data-width="88%"></div></div>
    </div>

    <div class="skill">
        <div class="skill-top"><span>JavaScript 交互开发</span><span>75%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar" data-width="75%"></div></div>
    </div>

    <div class="skill">
        <div class="skill-top"><span>响应式网页设计</span><span>80%</span></div>
        <div class="skill-bar-bg"><div class="skill-bar" data-width="80%"></div></div>
    </div>
</div>

<!-- 项目展示 -->
<div class="wrap" id="project">
    <h2 class="title">项目展示</h2>
    <div class="project-box">
        <div class="project-card">
            <h3>个人单页展示网站</h3>
            <p>采用原生前端技术开发，包含导航、技能、项目、表单完整模块，支持移动端自适应，动画流畅，结构规范。</p >
        </div>
        <div class="project-card">
            <h3>静态课程展示页面</h3>
            <p>多区块布局设计，配色简洁舒适，适合课程作业展示，代码整洁、注释完善，可直接部署上线。</p >
        </div>
        <div class="project-card">
            <h3>交互式留言表单</h3>
            <p>原生JS实现表单验证与提交提示，界面简约高级，交互友好，符合现代网页设计标准。</p >
        </div>
    </div>
</div>

<!-- 联系表单 -->
<div class="wrap" id="contact">
    <h2 class="title">联系我</h2>
    <form id="form">
        <div class="input-item">
            <label>姓名</label>
            <input type="text" placeholder="请输入姓名" required>
        </div>
        <div class="input-item">
            <label>邮箱</label>
            <input type="email" placeholder="请输入邮箱" required>
        </div>
        <div class="input-item">
            <label>留言内容</label>
            <textarea rows="5" placeholder="请输入留言内容" required></textarea>
        </div>
        <button type="submit">提交留言</button>
    </form>
</div>

<!-- 页脚 -->
<footer>
    <p>© 2026 个人主页 | 前端期末作业 原创设计</p >
</footer>

<script>
    // 进度条滚动动画
    window.onload = function(){
        let bars = document.querySelectorAll(".skill-bar");
        bars.forEach(item=>{
            item.style.width = item.dataset.width;
        })
    }

    // 平滑滚动
    let aTags = document.querySelectorAll(".nav-container a");
    aTags.forEach(a=>{
        a.onclick = function(e){
            e.preventDefault();
            document.querySelector(this.getAttribute("href")).scrollIntoView({behavior:"smooth"});
        }
    })

    // 表单提交提示
    document.getElementById("form").onsubmit = function(e){
        e.preventDefault();
        alert("提交成功！感谢您的留言！");
        this.reset();
    }
</script>
