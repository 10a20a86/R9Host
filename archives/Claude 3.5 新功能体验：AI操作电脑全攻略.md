# Claude 3.5 新功能体验：AI操作电脑全攻略

Claude 3.5 最新版本带来两大亮点：AI操作电脑和编程能力的大幅提升。本文将详细介绍如何在自己的电脑上体验Claude 3.5的操作电脑功能。

## 准备工作

在开始之前，确保你具备以下条件：

- 一台支持Docker的电脑（Windows、Mac或Linux均可）
- Claude的官方API密钥（目前大多数中转服务暂不支持，建议直接使用官方Key）

## Docker安装

首先，安装Docker并确保其正常运行。安装完成后，打开Docker并登录。确保左下角的服务状态为“启动成功”。

## 拉取镜像

Claude官方提供了一个Python示例代码，可以直接拉取到本地运行：

bash
docker run -v ${env:USERPROFILE}\.anthropic:/home/computeruse/.anthropic -p 5900:5900 -p 8501:8501 -p 6080:6080 -p 8080:8080 -it ghcr.io/anthropics/anthropic-quickstarts:computer-use-demo-latest


在本地Python环境（建议3.11以上版本）中安装依赖：

bash
pip install -r dev-requirement.txt


## 启动Claude

镜像拉取完成后，访问`http://localhost:8080`，按照提示操作即可。在侧边栏输入你的API密钥，即可开始体验。

## 功能体验

### 编写并运行贪吃蛇游戏

Claude不仅帮你安装了Pygame库，还能在1分钟内完成代码编写和运行：

python
# 示例代码
import pygame
# ...（省略代码）


### 测试游戏操作

通过截图获取当前游戏信息，Claude可以模拟操作。但由于截图和操作的时差，实际体验略有延迟。

### 搜索京东新闻

Claude正确打开浏览器并使用Google搜索，但有时会丢失部分关键词。

### 整理新闻到Excel

Claude能准确定位Excel单元格并输入新闻内容，尽管在标题行处理上稍有瑕疵。

### 查找北非蛋做法

在小红书搜索北非蛋的做法时，由于登录验证码和限速问题，任务未能顺利完成。

## 结论

Claude 3.5的AI操作电脑功能虽然强大，但交互步骤较多，导致任务执行速度较慢。随着技术优化，未来这一功能有望更加高效。

👉 [WildCard | 一分钟注册，轻松订阅海外线上服务](https://bbtdd.com/WildCard)