<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=yes">
    <title>时空胶囊 Space Capsule</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background: linear-gradient(135deg, #f5f7fc 0%, #e9eef5 100%);
            color: #1e2a3e;
            padding: 20px;
            min-height: 100vh;
        }

        .container {
            max-width: 1100px;
            margin: 0 auto;
            background: rgba(255,255,255,0.92);
            border-radius: 36px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.08), 0 4px 12px rgba(0,0,0,0.02);
            padding: 2rem 2rem 3rem;
            backdrop-filter: blur(2px);
            transition: all 0.2s ease;
        }

        .header-row {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            margin-bottom: 2rem;
            border-bottom: 2px solid rgba(100,108,255,0.2);
            padding-bottom: 1rem;
        }

        .logo-area {
            display: flex;
            align-items: baseline;
            gap: 12px;
            flex-wrap: wrap;
        }

        .logo-area h1 {
            font-size: 1.9rem;
            font-weight: 700;
            background: linear-gradient(120deg, #2b3b4e, #4a6a8b);
            background-clip: text;
            -webkit-background-clip: text;
            color: transparent;
            letter-spacing: -0.3px;
        }

        .lang-switch {
            display: flex;
            gap: 8px;
            background: #f0f2f6;
            padding: 5px 10px;
            border-radius: 60px;
            backdrop-filter: blur(4px);
        }

        .lang-btn {
            background: transparent;
            border: none;
            padding: 6px 18px;
            border-radius: 40px;
            font-size: 0.85rem;
            font-weight: 500;
            cursor: pointer;
            transition: 0.2s;
            color: #2c3e4e;
        }

        .lang-btn.active {
            background: #ffffff;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
            color: #3b6e9f;
            font-weight: 600;
        }

        .badge-group {
            margin-top: 12px;
            display: flex;
            flex-wrap: wrap;
            gap: 12px;
            justify-content: center;
            margin-bottom: 32px;
        }

        .badge-img {
            transition: transform 0.1s ease;
        }

        .section-title {
            font-size: 1.7rem;
            font-weight: 600;
            margin: 2rem 0 1rem 0;
            border-left: 5px solid #4f7ea0;
            padding-left: 18px;
            color: #1f3b4c;
        }

        .card-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 24px;
            justify-content: space-between;
        }

        .card {
            flex: 1;
            min-width: 230px;
            background: #ffffffdd;
            backdrop-filter: blur(4px);
            background: rgba(255,255,255,0.85);
            border-radius: 28px;
            padding: 1.2rem 1.2rem 1.8rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.05);
            transition: all 0.2s;
            border: 1px solid rgba(255,255,255,0.6);
        }

        .card h3 {
            font-size: 1.5rem;
            margin-bottom: 1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .download-list {
            list-style: none;
            margin: 1rem 0;
        }

        .download-list li {
            margin: 12px 0;
            display: flex;
            align-items: baseline;
            flex-wrap: wrap;
            gap: 10px;
            justify-content: space-between;
            border-bottom: 1px solid #e2e8f0;
            padding-bottom: 8px;
        }

        .store-badge {
            background: #2c5a7a20;
            padding: 4px 12px;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 500;
        }

        .btn-link {
            background: #2c5a7a;
            color: white;
            padding: 6px 16px;
            border-radius: 80px;
            text-decoration: none;
            font-size: 0.8rem;
            font-weight: 500;
            transition: 0.2s;
            display: inline-block;
        }

        .btn-link:hover {
            background: #1d405a;
            transform: scale(0.97);
        }

        .stats-badge {
            background: #eef2ff;
            border-radius: 24px;
            padding: 1rem;
            text-align: center;
            margin: 2rem 0;
        }

        .disclaimer {
            background: #fff6e0;
            border-left: 6px solid #e6a017;
            padding: 1rem 1.5rem;
            border-radius: 24px;
            margin: 2rem 0 1rem;
            font-size: 0.85rem;
            color: #664d03;
        }

        footer {
            text-align: center;
            margin-top: 2rem;
            font-size: 0.75rem;
            color: #5f6c7a;
        }

        @media (max-width: 680px) {
            .container {
                padding: 1.2rem;
            }
            .card-grid {
                flex-direction: column;
            }
            .header-row {
                flex-direction: column;
                align-items: flex-start;
                gap: 12px;
            }
        }
    </style>
</head>
<body>
<div class="container" id="app">
    <div class="header-row">
        <div class="logo-area">
            <h1 data-key="app_title">时空胶囊 Space Capsule</h1>
        </div>
        <div class="lang-switch">
            <button class="lang-btn" data-lang="zh">中文</button>
            <button class="lang-btn" data-lang="en">English</button>
        </div>
    </div>

    <div class="badge-group">
        <a href="https://github.com/xie237/space-capsule-update" target="_blank">
            <img class="badge-img" src="https://img.shields.io/badge/平台-Android-brightgreen" alt="Android">
        </a>
        <a href="https://github.com/xie237/space-capsule-update" target="_blank">
            <img class="badge-img" src="https://img.shields.io/badge/平台-HarmonyOS-red" alt="HarmonyOS">
        </a>
        <br>
        <a href="https://github.com/xie237">
            <img src="https://visitor-badge.laobi.icu/badge?page_id=xie237.space-capsule-update" alt="Visitor Count">
        </a>
        <br>
        <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black" alt="JavaScript">
        <img src="https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white" alt="Android">
    </div>

    <div class="section-title" data-key="android_title">📲 下载安装</div>
    <div class="card-grid">
        <div class="card">
            <h3>🤖 <span data-key="android_os">Android 用户</span></h3>
            <table style="width:100%; border-collapse: collapse;">
                <thead>
                <tr><th style="text-align:left;"><span data-key="version_type">版本类型</span></th><th style="text-align:left;"><span data-key="download_channel">下载渠道</span></th><th style="text-align:left;"><span data-key="desc_note">说明</span></th></tr>
                </thead>
                <tbody>
                    <tr><td>🚀 <span data-key="stable_ver">正式版</span></td><td><span data-key="huawei_app">华为应用市场</span> / <span data-key="tencent_app">腾讯应用宝</span></td><td><span data-key="stable_desc">稳定版本，推荐从应用商店下载</span></td></tr>
                    <tr><td>🧪 <span data-key="beta_ver">内测版</span></td><td><a href="https://github.com/xie237/space-capsule-update/releases/tag/v2.0.0-beta.1" target="_blank" class="btn-link" style="background:#5a6e7c;">GitHub 下载</a></td><td><span data-key="beta_desc">比赛展示版，包含社交功能</span></td></tr>
                </tbody>
            </table>
        </div>
        <div class="card">
            <h3>🌸 <span data-key="harmony_os">HarmonyOS 用户</span></h3>
            <table style="width:100%; border-collapse: collapse;">
                <thead><tr><th><span data-key="version_type">版本类型</span></th><th><span data-key="download_channel">下载渠道</span></th><th><span data-key="desc_note">说明</span></th></tr></thead>
                <tbody>
                    <tr><td>🚀 <span data-key="stable_ver">正式版</span></td><td><a href="https://appgallery.huawei.com/app/detail?id=com.zifeixun.campuscapsule&channelId=SHARE&source=appshare" target="_blank" class="btn-link">华为应用市场</a></td><td><span data-key="harmony_stable_desc">鸿蒙官方应用市场</span></td></tr>
                    <tr><td>🧪 <span data-key="beta_ver">内测版</span></td><td><span data-key="none_tip">暂无</span></td><td><span data-key="expect_tip">敬请期待</span></td></tr>
                </tbody>
            </table>
        </div>
    </div>

    <div class="section-title" data-key="stats_title">📊 统计数据</div>
    <div class="stats-badge">
        <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 32px;">
            <div><strong data-key="total_github_dl">GitHub 总下载次数</strong><br> <img src="https://img.shields.io/github/downloads/xie237/space-capsule-update/total?label=" alt="total downloads"></div>
            <div><strong data-key="latest_ver_dl">GitHub 最新正式版下载</strong><br> <img src="https://img.shields.io/github/downloads/xie237/space-capsule-update/latest/total?label=" alt="latest downloads"></div>
        </div>
    </div>

    <div class="disclaimer" data-key="disclaimer_text">
        ⚠️ 免责声明：内测版仅供比赛展示，社交功能由用户自行负责。违规内容将被删除并封禁账号。
    </div>

    <div class="section-title" data-key="repo_title">📝 仓库说明</div>
    <p style="background:#f8fafc; padding: 14px 20px; border-radius: 32px;" data-key="repo_desc">
        <code>space-capsule-update</code> —— 时空胶囊应用更新仓库
    </p>
    <footer>
        <span data-key="footer_note">时空胶囊 · 跨越时空的珍藏</span>
    </footer>
</div>

<script>
    const translations = {
        zh: {
            app_title: "时空胶囊 Space Capsule",
            android_title: "📲 下载安装",
            android_os: "Android 用户",
            version_type: "版本类型",
            download_channel: "下载渠道",
            desc_note: "说明",
            stable_ver: "正式版",
            huawei_app: "华为应用市场",
            tencent_app: "腾讯应用宝",
            stable_desc: "稳定版本，推荐从应用商店下载",
            beta_ver: "内测版",
            beta_desc: "比赛展示版，包含社交功能",
            harmony_os: "HarmonyOS 用户",
            harmony_stable_desc: "鸿蒙官方应用市场",
            none_tip: "暂无",
            expect_tip: "敬请期待",
            stats_title: "📊 统计数据",
            total_github_dl: "GitHub 总下载次数",
            latest_ver_dl: "GitHub 最新正式版下载",
            disclaimer_text: "⚠️ 免责声明：内测版仅供比赛展示，社交功能由用户自行负责。违规内容将被删除并封禁账号。",
            repo_title: "📝 仓库说明",
            repo_desc: "space-capsule-update —— 时空胶囊应用更新仓库",
            footer_note: "时空胶囊 · 跨越时空的珍藏"
        },
        en: {
            app_title: "Space Capsule",
            android_title: "📲 Download & Install",
            android_os: "Android Users",
            version_type: "Version",
            download_channel: "Channel",
            desc_note: "Description",
            stable_ver: "Stable",
            huawei_app: "Huawei AppGallery",
            tencent_app: "Tencent App Store",
            stable_desc: "Stable version, recommended from app store",
            beta_ver: "Beta",
            beta_desc: "Competition showcase version with social features",
            harmony_os: "HarmonyOS Users",
            harmony_stable_desc: "Official HarmonyOS AppGallery",
            none_tip: "None",
            expect_tip: "Coming soon",
            stats_title: "📊 Statistics",
            total_github_dl: "GitHub Total Downloads",
            latest_ver_dl: "GitHub Latest Release Downloads",
            disclaimer_text: "⚠️ Disclaimer: Beta version is only for competition showcase; social features are users' own responsibility. Violations will be removed and accounts banned.",
            repo_title: "📝 Repository Info",
            repo_desc: "space-capsule-update — Space Capsule app update repository",
            footer_note: "Space Capsule · Treasures across time"
        }
    };

    let currentLang = localStorage.getItem('spaceCapsuleLang') || 'zh';

    function setLanguage(lang) {
        if (!translations[lang]) return;
        currentLang = lang;
        localStorage.setItem('spaceCapsuleLang', lang);
        const elements = document.querySelectorAll('[data-key]');
        elements.forEach(el => {
            const key = el.getAttribute('data-key');
            if (translations[lang][key] !== undefined) {
                el.innerText = translations[lang][key];
            }
        });
        document.querySelectorAll('.lang-btn').forEach(btn => {
            const btnLang = btn.getAttribute('data-lang');
            if (btnLang === lang) {
                btn.classList.add('active');
            } else {
                btn.classList.remove('active');
            }
        });
    }

    function initLangToggle() {
        const btns = document.querySelectorAll('.lang-btn');
        btns.forEach(btn => {
            btn.addEventListener('click', (e) => {
                const lang = btn.getAttribute('data-lang');
                if (lang === 'zh') setLanguage('zh');
                else if (lang === 'en') setLanguage('en');
            });
        });
    }

    function renderInitialLanguage() {
        setLanguage(currentLang);
    }

    window.addEventListener('DOMContentLoaded', () => {
        initLangToggle();
        renderInitialLanguage();
    });
</script>
</body>
</html>