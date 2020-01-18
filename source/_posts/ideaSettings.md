---
title: IntelliJ IDEA 常用设置与插件汇总
subtitle: ideaSettings
categories:
- Work
tags: [IDE]
date: 2018-06-29 10:35:34
toc: true
---
关键词：IntelliJ IDEA；设置；插件；Java

<!-- more -->

## 1. Summary
- 这篇文章，通过配置 IDEA 的设置与插件，让我们的工具更加得心应手。
- 从 IDEA 14 逐渐到 IDEA 2019，记录常用的设置与插件。版本更新时，设置通过导出导入进行重用，插件需重装。
> 注：不同版本，Settings 菜单有所不同，用关键字进行搜索。以下目录结构参照 IDEA 2017。

## 2. Runtime Environment
- IntelliJ IDEA 14.0.5
- IntelliJ IDEA 15.0.2
- IntelliJ IDEA 2016.3.4
- IntelliJ IDEA 2017.3.3
- IntelliJ IDEA 2018.3
- IntelliJ IDEA 2019.3

### Windows
IDE's Java runtime: `IDEA_JDK_64` -> `%JAVA_HOME%`

`<product>64.exe` uses this JDK search sequence:
1. `IDEA_JDK_64` / `PHPSTORM_JDK_64` / `WEBIDE_JDK_64` / `PYCHARM_JDK_64` / `RUBYMINE_JDK_64` / `CL_JDK_64` / `DATAGRIP_JDK_64` / `GOLAND_JDK_64` environment variable
2. `idea.config.path\<product>64.jdk` file
3. `..\jre64` directory
4. system Registry
5. `JDK_HOME` environment variable
6. `JAVA_HOME` environment variable

Environment variable **must point to the JDK installation home directory**, for example: `c:\Program Files\Java\jdk1.8.0_112`

#### idea.config.path
- Windows Vista, 7, 8, 10: `<SYSTEM DRIVE>\Users\<USER ACCOUNT NAME>\.<PRODUCT><VERSION>`
- IntelliJ IDEA 14 Ultimate Edition: `C:\Users\Administrator\.IntelliJIdea14\`

#### Sub-directories
Under this directory you'll find the following sub-directories
- `config`: configuration (`idea.config.path`)
- `config\plugins`: plugins (`idea.plugins.path`)
- `system`: caches, local history, etc (`idea.system.path`)
- `system\log`: logs and thread dumps (`idea.log.path`)

## 3. Plugins
### General
- Eclipse code formatter
- Alibaba Java Coding Guidelines
- JRebel for IntelliJ

![EclipseCodeFormatter](https://www.wailian.work/images/2018/06/29/EclipseCodeFormatter-min.png)

### Optional
- Postfix Completion
- Lombok Plugin
- ZooKeeper
- BashSupport
- Lua

## 4. Settings
### Appearance & Behavior
取消自动更新

![Updates](https://www.wailian.work/images/2018/06/29/Updates-min.png)

### Editor
显示行号

![Appearance](https://www.wailian.work/images/2018/06/29/Appearance-min.png)

补全代码不区分大小写

![CodeCompletion](https://www.wailian.work/images/2018/06/29/CodeCompletion-min.png)

字体

![Font](https://www.wailian.work/images/2018/06/29/Font-min.png)

样式，Background: `C7EDCC`

![General](https://www.wailian.work/images/2018/06/29/General-min.png)

控制台字体

![ConsoleFont](https://www.wailian.work/images/2018/06/29/ConsoleFont-min.png)

tab设置

![CodeStyleJava](https://www.wailian.work/images/2018/06/29/CodeStyleJava-min.png)

![CodeStyleGeneral](https://www.wailian.work/images/2018/06/29/CodeStyleGeneral-min.png)

代码检查

![Inspections](https://www.wailian.work/images/2018/06/29/Inspections-min.png)

编码

![FileEncodings](https://www.wailian.work/images/2018/06/29/FileEncodings-min.png)

注释模版

![FileandCodeTemplates](https://www.wailian.work/images/2018/06/29/FileandCodeTemplates-min.png)

重新格式化代码

![ReformatCode](https://www.wailian.work/images/2018/06/29/ReformatCode-min.png)

### Build, Execution, Deployment
Java编译器，```Error:java: Compilation failed: internal java compiler error```

![JavaCompiler](https://www.wailian.work/images/2018/06/29/JavaCompiler17-min.png)

### Languages & Frameworks
Markdown默认布局

![Markdown](https://www.wailian.work/images/2018/06/29/Markdown-min.png)

## 5. Project Structure
项目SDK

![ProjectStructure](https://www.wailian.work/images/2018/06/29/ProjectStructure-min.png)

## 6. References
- [Selecting the JDK version the IDE will run under](https://intellij-support.jetbrains.com/hc/en-us/articles/206544879-Selecting-the-JDK-version-the-IDE-will-run-under)
- [Directories used by the IDE to store settings, caches, plugins and logs](https://intellij-support.jetbrains.com/hc/en-us/articles/206544519)