---
title: 如何用 ClawCloud 免费部署 AstrBot?
cover: https://api.imlazy.ink/img
tags: [编程, ClawCloud,免费,服务器,免费服务器,教程,Astrbot,Bot,Discord Bot,机器人]
categories: [ClawCloud]
date: 2026-03-04
description: 如何使用ClawCloud
articleGPT: 使用Clawcloud免费部署AstrBot的教程。
references:
  - title: 如何用 ClawCloud 免费部署 AstrBot?
    url: https://blog.1224hj.top/clawcloud-depoy-astrbot
---

::: tip 什么是ClawCloud?

ClawCloud Run 是一款创新的云计算解决方案，凭借其独特的架构和功能设计，为企业和开发者提供高效便捷的云使用体验。从搭建开发环境到管理数据存储，从快速创建应用程序到在线部署，它全面助力企业优化和创新数字化业务流程。

来自: [https://docs.run.claw.cloud/clawcloud-run/getting-started](https://docs.run.claw.cloud/clawcloud-run/getting-started)
:::

# ClawCloud 注册教程
::: details ClawCloud注册教程
### 1. 首先，请前往 [https://run.claw.cloud/pricing](https://run.claw.cloud/pricing)
![https://run.claw.cloud/pricing](/images/post/ClawCloud/run-claw-cloud-pricing-page.png)
### 2. 之后，点击右上角的"Get started"按钮，你会被跳转去：
![https://eu-central-1.run.claw.cloud/signin](/images/post/ClawCloud/run-claw-cloud-signin-page.png)
### 3. 使用GitHub注册/登录，之后授权、就好了（没那么难把？）
:::

## 你注册后，会到：
![https://eu-central-1.run.claw.cloud/](/images/post/ClawCloud/run-claw-cloud-main-page.png)
（推荐点击你头像→Plan→ 然后查看你是否有 $5 的"Monthly Gift"）

::: tip 什么是AstrBot?
AstrBot 是一个跨平台 AI 助手，让 AI 直接工作在你的聊天软件中，实现自动化任务与智能协作，同时提供灵活的 Agent 编排能力。

来自： [https://astrbot.app/](https://astrbot.app/)
:::

# AstrBot部署教程
1. 一旦你注册了、并且在ClawCloud主页，你就可以点击"App Launchpad"并进行下一步操作了
![https://eu-central-1.run.claw.cloud/](/images/post/ClawCloud/run-claw-cloud-main-page.png)
2. 到了"App Launchpad"界面后，点击"Create App"
3. 到了那个页面后推荐这样设置（点击图片可放大）：
![AstrBot Confuguration](/images/post/ClawCloud/astrbot-confuguration.png)

## Application Name: 
(Optional)

## Image:
::: radio checked
Public
:::
::: radio
Private
:::

### Image Name:
soulter/astrbot:latest

## Usage(这样设置才可以每个月一直用):
::: radio checked
Fixed
:::
::: radio
Scaling
:::
### Replicas:
1
### CPU:
0.5
### Memory:
1G

## Network
Container Port: 6185

Public Accesss: Yes

## Advanced Configuration
### Command
(留空)
#### Environment Variables(具体是不是必要我其实不知道):
```
ASTRBOT_PORT = 6185
TZ = Asia/Shanghai 
```
(或者其他你要的时区)

### Configmaps:
（留空）
### Local Storage:
/AstrBot/data => 1Gi

## 最后点击 "Depoy Aplication" 就可以成功部署了！

# 部署后，你可以等到在"Network"中的"Public Address"的链接显示"Aviailable"后，点击它给的免费域名就可以进入AstrBot的仪表盘了

::: danger AstrBot 注意事项
如果你安装过多插件，您将进入不了链接、所以并不建议您添加过多插件

（就像我，只安装了2个插件[分别是: "传话筒·立绘对话框"和"群分析总结插件"] 我就需要进入无痕模式并等待大量时间才能进入网站）


然后其实你也可以删文件的，在Pod List中：你可以在"OPERATION"找到一个类似文件夹的小图标，

点进去 然后会找到"plugins"什么的文件夹、然后在里面删（但在其他文件夹也许还会有缓存什么的）
:::
## 等太久了，累死我了！
若您在无痕模式等待的时间实在是太久了，你可以：
>
前往ClawCloud Dash:
![ClawCloud App Dash](/images/post/ClawCloud/ClawCloudAppDash.png)
>
然后，点击"Restart"然后等待就好

若您依旧重新再在无痕模式打开了网站还是很慢，你可以先点击"Pause"(注意，您的Bot也将无法使用) 并且等一会，然后再点击 "Continue" 然后应该就不会进不去了（但还要继续等会哦）

或若您已连接某个聊天平台，你可以在您已连接的使用该指令： `/dashboard_update `

::: tip AstrBot Links
接入消息平台教程： [https://docs.astrbot.app/platform/start.html](https://docs.astrbot.app/platform/start.html)

接入AI教程： [https://docs.astrbot.app/providers/start.html](https://docs.astrbot.app/providers/start.html)

插件：在AstrBot仪表盘的网站中点击 "插件>插件市场" 你就可以寻找并添加插件了
:::

::: warning
若有任何问题请您发送邮件到 1224huangjin@gmail.com 或者 在Discord添加用户名: 1224HuangJin 并且询问他(因为在这里的评论区我不一定会看)
:::

# 希望这篇文章有帮到你
