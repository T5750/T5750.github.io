---
title: Hexo GitHub 简明版博客搭建
subtitle: hexoBlog
categories:
- Work
tags: [Hexo, Git]
date: 2018-02-12 09:19:28
toc: true
---
## 1. 环境配置
[Node.js](https://nodejs.org/en/)(必须) 一路默认安装即可
安装[Git](http://git-scm.com/download/)(必须) 一路默认安装即可
[Github](http://github.com/)账号(必须)

### 1.1 Ubuntu
```
sudo ln -s /opt/node-v8.5.0-linux-x64/bin/node /usr/local/bin/node
sudo ln -s /opt/node-v8.5.0-linux-x64/bin/npm /usr/local/bin/npm
node -v
npm -v
```

### 1.2 设置淘宝镜像
```
sudo npm config set registry https://registry.npm.taobao.org //设置淘宝镜像
source ~/.bashrc //使修改立即生效
```

<!-- more -->

## 2. Hexo
右键打开`git bash`安装hexo
```
npm install -g hexo-cli
```
### 2.1 init
```
hexo init
npm install
```
### 2.2 server
```
hexo s //hexo server
```
浏览器中输入 http://localhost:4000/
此时，会有一篇文章`hello world`，对应的文件为 `hexo/source/_posts/hello-world.md`
文章用[markdown](https://www.zybuluo.com/mdeditor)语法写

### 2.3 新建文章
```
hexo new "New article"
```
会新建一个名为`New article`的文章，执行以下命令之后查看
```
hexo g //hexo generate //生成静态网页以及css js文件 存放于public文件夹中
hexo s
```

## 3. GitHub
新建repository，项目名: `T5750.github.io`

### 3.1 部署
在hexo文件夹中有个重要的文件`_config.yml`，打开编辑，把`T5750`换成你的账号名
```
deploy:
  type: git
  repo: git@github.com:T5750/T5750.github.io.git
  branch: master
```
执行下列命令后部署(部署前，需要配置SSH，否则失败)
```
hexo g
hexo d //hexo deploy　　//上传至GitHub 代替 git push...
```
至此，个人博客搭建完成

### 3.2 外配置SSH
打开`git bash`，设置`username`和`email`
```
git config --global user.name "test"
git config --global user.email "test@gmail.com"
```
生成密钥
```
ssh-keygen -t rsa -C "test@gmail.com"
```
最后得到`id_rsa`和`id_rsa.pub`两个文件，把`id_rsa.pub`的内容粘贴到GitHub中即可

## 4. Hexo Theme
### 4.1 Hexo Theme Next
#### 4.1.1 下载
GitHub clone到你的博客目录\themes目录下(`hexo/themes`下)
```
git clone git@github.com:iissnan/hexo-theme-next.git
```

#### 4.1.2 使用
打开站点总配置`_config.yml`(即`hexo/_config.yml`)，找到theme换成next即可(`theme: next`)，记得每一个冒号后面要有一个空格

### 4.2 Hexo Theme Yilia

#### 4.2.1 安装
```
git clone https://github.com/litten/hexo-theme-yilia.git themes/yilia
```

#### 4.2.2 配置
修改hexo根目录下的 `_config.yml` ： `theme: yilia`

#### 4.2.3 更新
```
cd themes/yilia
git pull
```

#### 4.2.4 文章截断
```
<!-- more -->
```

#### 4.2.5 Gitment评论
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

#### 4.2.6 不蒜子访问量统计
`hexo/themes/yilia/layout/_partial/footer.ejs`引入`busuanzi.js`
```
<script async src="//dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js"></script>
```
站点总访问量`hexo/themes/yilia/layout/_partial/footer.ejs`
```
<i style="font-size:12px;" class="icon-smile" title="访问量"></i> <span style="font-size:12px;" title="访问量"><span id="busuanzi_value_site_pv"></span>次访问</span>
```
单页面访问量`hexo/themes/yilia/layout/_partial/article.ejs`
```
<%- partial('post/category') %>
<%if(!index){%>
	<i class="icon-smile" title="阅读次数"></i> <span style="font-size:14px;" title="阅读次数"><span id="busuanzi_value_page_pv"></span>人阅读</span>
<% } %>
```

## 5. References
- [Hexo+Next搭建GitHub个人静态博客](http://www.cnblogs.com/cnfanhua/p/5167191.html)
- [史上最详细的Hexo博客搭建图文教程](https://xuanwo.org/2015/03/26/hexo-intor/#%E4%BD%BF%E7%94%A8hexo)
- [指令 | Hexo](https://hexo.io/zh-cn/docs/commands.html)
- [hexo-theme-next](https://github.com/iissnan/hexo-theme-next)
- [hexo-theme-yilia](https://github.com/litten/hexo-theme-yilia)
- [Gitment](https://github.com/imsun/gitment)
- [Gitment系统Validation Failed问题的解决](http://www.xjdesyxx.top/2018/02/07/errsln/)
- [Hexo Yilia主题增加分享以及访问统计](https://www.jianshu.com/p/cb0a105d7a81)
