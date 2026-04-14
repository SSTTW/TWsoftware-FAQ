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
  <a href="./" style="color: #666; text-decoration: underline;">返回首頁</a>
</div>
