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
### 5.1 Google Sitemap
```
npm install hexo-generator-sitemap --save
```
`hexo/_config.yml`配置
```
sitemap:
    path: sitemap.xml

skip_render:
  - googleb37eb5fa38914e1c.html
```
- 向[Google站长工具](https://www.google.com/webmasters/tools/home?hl=zh-CN)提交sitemap。
- 通过HTML文件方式验证通过后，在站点里选择 抓取->站点地图里 添加/测试站点地图。

### 5.2 Baidu Sitemap
```
npm install hexo-generator-baidu-sitemap --save
```

- [链接提交](https://ziyuan.baidu.com/linksubmit/url)
- [添加网站](http://zhanzhang.baidu.com/site/siteadd)
	1. 输入网站
	2. 站点属性
	3. 验证网站，选择文件验证，下载`baidu_verify_KoktB8hGH2.html`到`source`目录下

`hexo/_config.yml`配置
```
baidusitemap:
    path: baidusitemap.xml

skip_render:
  - baidu_verify_KoktB8hGH2.html
```

## 6. References
- [Hexo 主题优化](http://cighao.com/2016/02/14/optimization-of-hexo/)
- [动动手指，不限于NexT主题的Hexo优化（SEO篇）](http://www.arao.me/2015/hexo-next-theme-optimize-seo/)
- [Hexo博客配置优化](http://www.heqiangfly.com/2016/01/11/blog-hexo-optimize/)
