---
layout: default
title: MOTW 技術專欄
---

<style>
  body { color: #333; background-color: #ffffff; line-height: 1.8; font-family: "Helvetica Neue", Helvetica, Arial, sans-serif; }
  h1 { color: #D21F3C !important; border-bottom: 2px solid #D21F3C !important; padding-bottom: 12px; margin-top: 40px; }
  .site-footer, footer { display: none !important; }
  a { text-decoration: none; }

  /* 部落格卡片設計 */
  .blog-grid { display: flex; flex-direction: column; gap: 20px; margin-top: 30px; }
  
  .blog-card {
    border: 1px solid #eee;
    border-radius: 8px;
    padding: 20px;
    background-color: #fafafa;
    transition: all 0.3s ease;
    display: block;
    color: #333;
  }
  
  .blog-card:hover {
    border-color: #D21F3C;
    background-color: #ffffff;
    box-shadow: 0 4px 15px rgba(210, 31, 60, 0.1);
    transform: translateY(-2px);
  }

  .blog-date { font-size: 0.85em; color: #888; margin-bottom: 8px; }
  .blog-title { font-size: 1.3em; font-weight: bold; color: #D21F3C; margin: 0 0 10px 0; }
  .blog-excerpt { font-size: 0.95em; color: #666; margin: 0; }
</style>

# 📰 MOTW 技術專欄與手冊解析

這裡收錄了 PROFIS Engineering 軟體的進階應用指南與 Hilti 解決方案的技術解析，協助工程師掌握最先進的設計邏輯。

<div style="text-align: center; margin: 30px 0; position: relative;">
  本技術庫整合了軟體操作、力學原理及最新規範
  <div style="margin-top: 10px;">
    <form id="search-form" onsubmit="return handleSearch(event)">
      <input type="text" id="search-input" placeholder="🔍 輸入關鍵字搜尋文章 (例如：ACI 318, 植筋)..." 
        style="padding: 12px 20px; width: 100%; max-width: 500px; box-sizing: border-box; border-radius: 50px; border: 2px solid #fee2e5; font-size: 16px; outline: none; box-shadow: 0 4px 10px rgba(0,0,0,0.05);">
    </form>
  </div>
  <ul id="results-container" style="list-style: none; padding: 0; text-align: left; max-width: 500px; margin: 10px auto; background: white; border-radius: 12px; position: absolute; left: 0; right: 0; z-index: 1000; box-shadow: 0 10px 25px rgba(0,0,0,0.1);"></ul>
</div>

<script>
function handleSearch(event) {
  event.preventDefault(); // 防止頁面刷新
  const query = document.getElementById('search-input').value;
  if (query.trim() !== "") {
    // 這裡使用 Google 站內搜尋技術，會自動搜尋你指定的網址
    // 請將 site: 後面的網址換成你 FAQ 實際的網域 (例如: hilti.com.tw 或 github.io)
    const siteDomain = window.location.hostname; 
    const searchUrl = `https://www.google.com/search?q=site:${siteDomain}+${encodeURIComponent(query)}`;
    window.open(searchUrl, '_blank'); // 在新視窗打開搜尋結果
  }
  return false;
}
</script>

<div class="blog-grid">
  {% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="blog-card">
    <div class="blog-date">🗓️ {{ post.date | date: "%Y年 %m月 %d日" }}</div>
    <h3 class="blog-title">{{ post.title }}</h3>
    <p class="blog-excerpt">{{ post.excerpt }}</p>
  </a>
  {% endfor %}
</div>

<div style="margin-top: 40px; text-align: center;">
  <a href="/TWsoftware-FAQ/" style="color: #666; text-decoration: underline;">返回首頁</a>
</div>

<script src="https://cdn.jsdelivr.net/npm/simple-jekyll-search@1.10.0/dest/simple-jekyll-search.min.js"></script>
<script>
  SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/TWsoftware-FAQ/search.json',
    searchResultTemplate: '<li style="padding: 15px; border-bottom: 1px solid #f0f0f0;"><a href="{url}" style="color: #D21F3C; font-weight: bold; text-decoration: none; display: block;">{title}</a></li>',
    noResultsText: '<li style="padding: 15px; color: #888; text-align:center;">找不到相關文章 😢，請嘗試其他關鍵字。</li>'
  });
</script>
