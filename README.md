<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <!-- 移动端适配核心标签 -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>我的个人主页 | 个人介绍网站</title>
    <style>
        /* 全局样式重置 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: "Microsoft YaHei", system-ui, sans-serif;
        }
        :root {
            /* 清新蓝色主题配色变量，统一管理颜色 */
            --primary: #2575fc;
            --light-blue: #e8f2ff;
            --dark-blue: #0f48a8;
            --gray: #f5f7fa;
            --text: #333;
        }
        body {
            color: var(--text);
            background-color: #fff;
            line-height: 1.7;
        }

        /* 导航栏样式 */
        header nav {
            background-color: var(--primary);
            padding: 16px 0;
            position: sticky;
            top: 0;
            z-index: 999;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }
        .nav-wrap {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            gap: 36px;
            flex-wrap: wrap;
            padding: 0 20px;
        }
        .nav-wrap a {
            color: white;
            text-decoration: none;
            font-size: 16px;
            transition: 0.3s ease;
        }
        .nav-wrap a:hover {
            color: #cce3ff;
            transform: translateY(-2px);
        }

        /* Banner头像区域 */
        .banner {
            background: linear-gradient(135deg, var(--light-blue), #d0e4ff);
            padding: 60px 20px;
            text-align: center;
        }
        .avatar {
            width: 140px;
            height: 140px;
            border-radius: 50%;
            background-color: var(--primary);
            margin: 0 auto 20px;
            /* 简易头像占位，可替换为图片 */
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 48px;
            font-weight: bold;
            border: 4px solid #fff;
            box-shadow: 0 4px 12px rgba(37, 117, 252, 0.25);
        }
        .banner h1 {
            font-size: 32px;
            color: var(--dark-blue);
            margin-bottom: 8px;
        }
        .banner p {
            font-size: 17px;
            color: #444;
        }

        /* 通用内容容器 */
        .container {
            max-width: 1100px;
            margin: 60px auto;
            padding: 0 20px;
        }
        .section-title {
            font-size: 26px;
            color: var(--dark-blue);
            margin-bottom: 24px;
            padding-bottom: 10px;
            border-bottom: 3px solid var(--primary);
            display: inline-block;
        }

        /* 关于我模块 */
        #about p {
            font-size: 16px;
            color: #444;
            text-indent: 2em;
        }

        /* 技能进度条模块 */
        .skill-item {
            margin-bottom: 22px;
        }
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 6px;
        }
        .progress-box {
            width: 100%;
            height: 10px;
            background-color: #e2e8f0;
            border-radius: 10px;
            overflow: hidden;
        }
        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), #63a4ff);
            border-radius: 10px;
            transition: width 1s ease-in-out;
        }

        /* 项目卡片区域 */
        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 24px;
        }
        .project-card {
            background: var(--gray);
            padding: 24px;
            border-radius: 12px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.08);
            transition: 0.3s;
        }
        .project-card:hover {
            transform: translateY(-6px);
            box-shadow: 0 8px 20px rgba(37, 117, 252, 0.18);
        }
        .project-card h3 {
            color: var(--dark-blue);
            margin-bottom: 12px;
        }

        /* 联系表单模块 */
        #contact form {
            max-width: 600px;
        }
        .form-row {
            margin-bottom: 18px;
        }
        .form-row label {
            display: block;
            margin-bottom: 6px;
            font-weight: 500;
        }
        .form-row input,
        .form-row textarea {
            width: 100%;
            padding: 12px 14px;
            border: 1px solid #cbd5e1;
            border-radius: 8px;
            font-size: 15px;
            outline: none;
            transition: 0.3s;
        }
        .form-row input:focus,
        .form-row textarea:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 3px rgba(37, 117, 252, 0.15);
        }
        textarea {
            min-height: 120px;
            resize: vertical;
        }
        button.submit-btn {
            background-color: var(--primary);
            color: white;
            border: none;
            padding: 14px 36px;
            border-radius: 8px;
            font-size: 16px;
            cursor: pointer;
            transition: 0.3s;
        }
        button.submit-btn:hover {
            background-color: var(--dark-blue);
        }

        /* 页脚 */
        footer {
            background-color: var(--dark-blue);
            color: white;
            text-align: center;
            padding: 30px 20px;
            margin-top: 80px;
        }

        /* 移动端适配 */
        @media (max-width: 600px) {
            .nav-wrap {
                gap: 20px;
            }
            .banner h1 {
                font-size: 26px;
            }
            .avatar {
                width: 110px;
                height: 110px;
                font-size: 36px;
            }
            .section-title {
                font-size: 22px;
            }
        }
    </style>
</head>
<body>
    <!-- 导航栏区域 -->
    <header>
        <nav>
            <div class="nav-wrap">
                <a href=" ">首页</a >
                <a href="#about">关于我</a >
                <a href="#skill">专业技能</a >
                <a href="#project">项目展示</a >
                <a href="#contact">联系方式</a >
            </div>
        </nav>
    </header>

    <!-- Banner头像首页区域 -->
    <section class="banner" id="home">
        <div class="avatar">我</div>
        <h1>你的姓名</h1>
        <p>计算机专业学生 | 前端网页开发爱好者</p >
    </section>

    <!-- 关于我模块 -->
    <section class="container" id="about">
        <h2 class="section-title">关于我</h2>
        <p>
            我是一名在校计算机专业学生，专注于Web前端静态页面开发，熟练掌握HTML、CSS、JavaScript基础开发技术。本次个人网站通过AI辅助完成UI设计与代码编写，页面采用清新蓝色简约风格，全面适配手机、平板、电脑等不同尺寸设备。日常热衷于网页界面美化、静态网站部署，擅长制作轻量化、无外部依赖的单页展示网站。
        </p >
    </section>

    <!-- 技能进度条模块 -->
    <section class="container" id="skill">
        <h2 class="section-title">专业技能</h2>
        <div class="skill-list">
            <!-- HTML技能 -->
            <div class="skill-item">
                <div class="skill-name">
                    <span>HTML静态页面</span>
                    <span>90%</span>
                </div>
                <div class="progress-box">
                    <div class="progress-bar" style="width: 90%"></div>
                </div>
            </div>
            <!-- CSS技能 -->
            <div class="skill-item">
                <div class="skill-name">
                    <span>CSS布局与美化</span>
                    <span>85%</span>
                </div>
                <div class="progress-box">
                    <div class="progress-bar" style="width: 85%"></div>
                </div>
            </div>
            <!-- JS技能 -->
            <div class="skill-item">
                <div class="skill-name">
                    <span>JavaScript基础交互</span>
                    <span>70%</span>
                </div>
                <div class="progress-box">
                    <div class="progress-bar" style="width: 70%"></div>
                </div>
            </div>
            <!-- 网站部署技能 -->
            <div class="skill-item">
                <div class="skill-name">
                    <span>Gitee/GitHub静态部署</span>
                    <span>78%</span>
                </div>
                <div class="progress-box">
                    <div class="progress-bar" style="width: 78%"></div>
                </div>
            </div>
        </div>
    </section>

    <!-- 项目卡片展示模块 -->
    <section class="container" id="project">
        <h2 class="section-title">项目展示</h2>
        <div class="project-grid">
            <!-- 项目卡片1 -->
            <div class="project-card">
                <h3>个人单页介绍网站</h3>
                <p>本次期末大作业作品，纯HTML+内嵌CSS+JS开发，无外部cdn资源，支持移动端自适应，可一键部署至Gitee Pages公网访问。</p >
            </div>
            <!-- 项目卡片2 -->
            <div class="project-card">
                <h3>简易在线表单页面</h3>
                <p>基于原生JS实现数据提交交互，包含输入校验、弹窗提示功能，页面采用蓝色简约设计，轻量化无插件依赖。</p >
            </div>
            <!-- 项目卡片3 -->
            <div class="project-card">
                <h3>课程作业展示页面</h3>
                <p>多模块分栏布局，包含作业列表、技能进度、个人简介三大核心板块，适配手机端纵向浏览。</p >
            </div>
        </div>
    </section>

    <!-- 联系表单模块 -->
    <section class="container" id="contact">
        <h2 class="section-title">联系我</h2>
        <form id="contactForm">
            <div class="form-row">
                <label>你的姓名</label>
                <input type="text" name="username" placeholder="请输入姓名" required>
            </div>
            <div class="form-row">
                <label>电子邮箱</label>
                <input type="email" name="email" placeholder="请输入邮箱地址" required>
            </div>
            <div class="form-row">
                <label>留言内容</label>
                <textarea name="msg" placeholder="写下你想说的内容..." required></textarea>
            </div>
            <button type="submit" class="submit-btn">提交留言</button>
        </form>
    </section>

    <!-- 页脚区域 -->
    <footer>
        <p>© 2026 个人主页 | 期末大作业 · 纯原生前端开发</p >
    </footer>

    <!-- JS交互代码，全部内嵌无外部依赖 -->
    <script>
        // 1. 表单提交弹窗提示
        const form = document.getElementById('contactForm');
        form.addEventListener('submit', function(e) {
            // 阻止表单默认刷新行为
            e.preventDefault();
            alert('留言提交成功！我会尽快查看你的消息~');
            // 清空表单内容
            form.reset();
        })

        // 2. 平滑滚动（点击导航跳转页面无卡顿）
        const navLinks = document.querySelectorAll('.nav-wrap a');
        navLinks.forEach(link => {
            link.addEventListener('click', function(e) {
                e.preventDefault();
                // 获取跳转目标id
                const targetId = this.getAttribute('href');
                const targetDom = document.querySelector(targetId);
                // 平滑滚动到对应区块
                targetDom.scrollIntoView({
                    behavior: 'smooth'
                })
            })
        })

        // 3. 页面加载动画：进度条动态加载效果
        window.addEventListener('load', function() {
            const bars = document.querySelectorAll('.progress-bar');
            bars.forEach(bar => {
                // 先清空宽度，再延迟恢复实现动画
                const originWidth = bar.style.width;
                bar.style.width = '0';
                setTimeout(() => {
                    bar.style.width = originWidth;
                }, 300)
            })
        })
    </script>
</body>
</html>
