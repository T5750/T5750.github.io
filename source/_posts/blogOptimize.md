---
title: Hexo GitHub 简明版博客优化
subtitle: blogOptimize
categories:
- Work
tags: [Hexo, Git]
date: 2018-02-23 10:35:28
toc: true
---
关键词：配置；统计；评论；Sitemap

<!-- more -->

## 1. 环境配置
基于 [hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)

## 2. 统计分析
### 2.1 百度统计
1. 注册并登录 [百度统计](http://tongji.baidu.com/)
1. 代码管理-代码获取-复制代码到`hexo/themes/yilia/_config.yml`中的`baidu_analytics`

### 2.2 Google Analytics（分析）
1. 注册 [Google Analytics（分析）](https://analytics.google.com)
1. 添加跟踪代码-复制代码到`hexo/themes/yilia/_config.yml`中的`google_analytics`

## 3. 评论
### 3.1 Gitment评论
1.注册 [OAuth Application](https://github.com/settings/applications/new)
2.引入 Gitment
```
gitment_owner: T5750 #你的 GitHub ID
gitment_repo: 'T5750.github.io' #存储评论的 repo
gitment_oauth:
  client_id: #client ID
  client_secret: #client secret
```
3.初始化评论

### 3.2 来必力
1. 注册并登录 [来必力](https://livere.com/login_form)
1. 安装来必力-[代码管理](https://livere.com/insight/myCode)-复制代码到`hexo/themes/yilia/layout/_partial/article.ejs`

### 3.3 CommentHub
1. 注册 [CommentHub](https://commenthub.github.io/)，设置Website
1. 引入 CommentHub
```
<script type="text/javascript">
    var commenthub_id = YOUR_ID;
    var commenthub_website = YOUR_DOMAIN;//https://commenthub.github.io
    var commenthub_identifier = YOUR_POST_ID;//https://commenthub.github.io/index.html
    var commenthub_url = YOUR_POST_URL;//https://commenthub.github.io/index.html
    var commenthub_title = YOUR_POST_TITLE;//CommentHub Example
    (function () {
        var dsq = document.createElement('script');
        dsq.type = 'text/javascript';
        dsq.async = true;
        dsq.src = 'https://commenthub.herokuapp.com/js/embed.js';
        (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    }());
</script>
<div id="commenthub_thread" style="margin: 0;padding: 0;border: 0;font: inherit;font-size: 100%;vertical-align: baseline;"></div>
```

### 3.4 Disqus
1. 注册 [Disqus](https://disqus.com/profile/signup/)
1. Settings -> [Add Disqus To Site](https://disqus.com/features/engage/) -> GET STARTED -> [I want to install Disqus on my site](https://disqus.com/profile/signup/intent/) -> [Create a new site](https://disqus.com/admin/create/) (Website Name, Category, Language)
1. I don't see my platform listed, install manually with Universal Code -> Configure Disqus (Shortname, Website Name, Website URL)
```
disqus: true
disqus_shortname: evaneo
```

### 3.5 Gitalk
1. [GitHub Application](https://github.com/settings/applications/new), Authorization callback URL: `https://t5750.github.io/`
1. `npm i --save gitalk`
```
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script>
<div id="gitalk-container"></div>
<script type="text/javascript">
  var gitalk = new Gitalk({
    clientID: 'GitHub Application Client ID',
    clientSecret: 'GitHub Application Client Secret',
    repo: 'GitHub repo',
    owner: 'GitHub repo owner',
    admin: ['GitHub repo owner and collaborators, only these guys can initialize github issues'],
    id: location.pathname,      // Ensure uniqueness and length less than 50
    distractionFreeMode: false  // Facebook-like distraction free mode
  })
  gitalk.render('gitalk-container')
</script>
```

## 4. RSS
```
npm install hexo-generator-feed
```
`hexo/themes/yilia/_config.yml`配置
```
rss: "/atom.xml"
```

## 5. Sitemap
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
- 搜索`site:evaneo.top`

### 5.2 Baidu Sitemap
```
npm install hexo-generator-baidu-sitemap --save
```

- [链接提交](https://ziyuan.baidu.com/linksubmit/url)
- [添加网站](https://ziyuan.baidu.com/site/siteadd)
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

### 5.3 Bing Sitemap
[提交网址到必应](https://www.bing.com/toolbox/submit-site-url)
- 输入主页的 URL，图片中的文字，提交
- 添加 sitemap
- 下载`BingSiteAuth.xml`，验证

### 5.4 360 Sitemap
- [提交您的网站](http://info.so.com/site_submit.html)
- [360站长平台](http://zhanzhang.so.com/)

### 5.5 Sogou Sitemap
- [网站收录](https://fankui.sogou.com/index.php/web/web/index)
- [搜狗站长平台](http://zhanzhang.sogou.com/index.php/site/index)

## 6. HTML页面
### 6.1 404公益页面
腾讯404公益页面`source/404.html`
```
<script type="text/javascript" charset="utf-8">
	var domain='https://qzonestyle.gtimg.cn/qzone_v6/lostchild/';
</script>
<script type="text/javascript" src="https://qzonestyle.gtimg.cn/qzone_v6/lostchild/data.js"></script>
<script type="text/javascript" src="https://qzonestyle.gtimg.cn/qzone_v6/lostchild/page.js"></script>
```

### 6.2 多合一收款二维码
多合一收款二维码`source/oneQRCode.html`
```
qqUrl: "https://i.qianbao.qq.com/wallet/sqrcode.htm?m=tenpay&a=1&u=1097437863&ac=B4C5BACD47FE6936D4B6DD29D866E1FC3AEA141B073F9DD94DE6404509CEE0FA&n=孤帆远影&f=wallet",
wechatUrl: "https://wx.tenpay.com/f2f?t=AQAAAFtDAYCgnh0H4NWppc2G0n0%3D",
aliUrl: "HTTPS://QR.ALIPAY.COM/FKX05202GE16QHOXXX7NE6",
```
[多合一收款二维码体验链接](/oneQRCode.html)

## 7. 域名
### 7.1 万网
- 注册域名 [evaneo.top](http://evaneo.top)
- 实名认证
- 修改域名DNS

### 7.2 DNSPod
- 登录 [DNSPod](https://www.dnspod.cn/Login)
- 域名解析-添加域名-添加记录
```
@       A      默认  192.30.252.153
@       A      默认  192.30.252.154
@       CNAME  国内  gitcafe.io.
www     CNAME  默认  jackroyal.github.io.
www     CNAME  国内  gitcafe.io.
```

## 8. References
- [Hexo 主题优化](http://cighao.com/2016/02/14/optimization-of-hexo/)
- [动动手指，不限于NexT主题的Hexo优化（SEO篇）](http://www.arao.me/2015/hexo-next-theme-optimize-seo/)
- [Hexo博客配置优化](http://www.heqiangfly.com/2016/01/11/blog-hexo-optimize/)
- [Gitment](https://github.com/imsun/gitment)
- [Gitment系统Validation Failed问题的解决](http://www.xjdesyxx.top/2018/02/07/errsln/)
- [使腾讯404公益页面支持HTTPS](https://eason-yang.com/2016/08/06/set-tencent-lostchild-404-page-for-ssl/)
- [解决 Github Pages 禁止百度爬虫的方法](https://bblove.me/2015/11/25/how-to-solve-the-problem-that-github-blocks-the-baidu-spider/)
- [解决 Github Pages 禁止百度爬虫的方法2--从gitcafe迁移到coding.net](https://bblove.me/2016/03/06/migrate-pages-from-gitcafe-to-coding/)
- [CommentHub Example](https://commenthub.github.io/)
- [多合一收款二维码原理及实现(源码)](https://mkblog.cn/922/)
- [Gitalk](https://github.com/gitalk/gitalk)