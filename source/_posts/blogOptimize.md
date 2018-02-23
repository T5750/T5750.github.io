---
title: Hexo GitHub 简明版博客优化
subtitle: blogOptimize
categories:
- Work
tags: [Hexo, Git]
date: 2018-02-23 10:35:28
---
## 1. 环境配置
基于 [hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)

## 2. 百度统计
1. 注册并登录 [百度统计](http://tongji.baidu.com/)
1. 代码管理-代码获取-复制代码到`hexo/themes/yilia/_config.yml`中的`baidu_analytics`

## 3. 来必力
1. 注册并登录 [来必力](http://laibili.com.cn/login_form)
1. 安装来必力-代码管理-复制代码到`hexo/themes/yilia/layout/_partial/article.ejs`

<!-- more -->

## 4. 添加 RSS
```
npm install hexo-generator-feed
```
`hexo/themes/yilia/_config.yml`配置
```
rss: "/atom.xml"
```

## 5. 添加 Sitemap
```
npm install hexo-generator-sitemap
```
`hexo/_config.yml`配置
```
sitemap:
    path: sitemap.xml
```

## 6. References
- [Hexo 主题优化](http://cighao.com/2016/02/14/optimization-of-hexo/)
