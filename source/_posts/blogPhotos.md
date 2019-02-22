---
title: Hexo GitHub 简明版博客相册
subtitle: blogPhotos
categories:
  - Work
date: 2018-03-09 09:00:49
tags: [Hexo]
---
## 1. 环境配置
- 基于 [hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)
- 图片来自 [外链工厂](https://www.wailian.work/)

## 2. 外链工厂

<!-- more -->

注册-登录-上传图片

## 3. 配置相册
### 3.1 新建相册页面
```
hexo new page photos
```
删除`index.md`

### 3.2 相册代码
copy如下代码到`photos`
- [index.ejs](https://github.com/T5750/T5750.github.io/blob/hexo/source/photos/index.ejs)
- [ins.css](https://github.com/T5750/T5750.github.io/blob/hexo/source/photos/ins.css)
- [ins.js](https://github.com/T5750/T5750.github.io/blob/hexo/source/photos/ins.js)
- [ins.json](https://github.com/T5750/T5750.github.io/blob/hexo/source/photos/ins.json)

copy [empty.png](https://github.com/T5750/T5750.github.io/blob/hexo/source/assets/images/empty.png) 到`source/assets/images`

配置`yilia/_config.yml`
```
menu:
  主页: /
  相册: /photos/index.html
```

### 3.3 配置`ins.json`
参照修改`date`, `link`, `text`等（`link`从上传[外链工厂](https://www.wailian.work/)的图片中截取）
```
{
	"list": [{
		"date": "2018-03",
		"arr": {
			"year": 2018,
			"month": 3,
			"src": ["", ""],
			"link": ["2018/03/08/LongTailedBushtits","2018/03/08/HallstattAustria"],
			"text": ["Long Tailed Bushtits","Hallstatt Austria"],
			"type": ["image", "image"]
		}
	}]
}
```

### 3.4 最终效果
- [相册](/photos/index.html)

![photos](https://www.wailian.work/images/2018/03/09/photos-min.png)

## 4. References
- [BlogBackup](https://github.com/litten/BlogBackup)