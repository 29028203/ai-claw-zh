# 小龙虾OpenClaw保姆级教程分享

> 原文链接：[https://www.laoshoucun.com/openclawzn/2069](https://www.laoshoucun.com/openclawzn/2069)

<p>最近不管是在抖音、知乎还是各大技术交流群，大家都在互相对暗号：“今天你养龙虾了吗？”很多新手看了一头雾水，这篇文章就用大白话给大家彻底讲透，到底什么是“养龙虾”，以及你怎么才能在自己的电脑或手机上养一只😉（虽然本人已经养死两只了😂）</p>
<p><strong>一、背景科普：“龙虾”到底是个啥？</strong><br />
1. 它是谁？<br />
它的真名叫 OpenClaw，是一个开源的AI智能体（AI Agent）系统。因为它的吉祥物是一只红色龙虾，所以国内网友都戏称玩这个软件叫“养龙虾”。</p>
<p>2. 它和文心、豆包、ChatGPT有啥区别？<br />
用一句话总结：ChatGPT是你的“顾问”，而OpenClaw是你的“打工人”。用ChatGPT时，你问它一个问题，它只会给你一段文字回答，剩下的复制粘贴、发邮件、写文档都得自己动手。用OpenClaw就不一样了：你可以直接把它绑定到QQ、企业微信、飞书或者Telegram上。比如你发一条语音：“帮我把昨天收件箱里的客户投诉邮件整理成一个Excel发给我”，它就会自己打开邮箱、提取内容、生成表格，最后把文件发回你的聊天框。它甚至能自己上网搜索、写代码、操作你的电脑浏览器。通俗一点说，它就像过年时薅羊毛自动点外卖的千问的增强版，只不过千问只能控制阿里系的部分功能，而<a href="https://www.laoshoucun.com/">OpenClaw</a>可以控制整个电脑（包括系统权限）🤯。</p>
<p><strong>二、安装教程：小白也能一键部署</strong><br />
很多新手觉得搞AI必须得懂编程，其实完全不用！现在部署方式非常多样，下面按推荐顺序给大家整理了一套保姆级方案。</p>
<p>方案一：官网一键脚本安装（推荐）<br />
第一步：获取安装脚本<br />
打开浏览器，访问OpenClaw官网（openclaw.ai），下拉页面找到「Quick Start」部分，根据自己的操作系统型号复制对应的安装代码。</p>
<p><img loading="lazy" decoding="async" class="alignnone wp-image-2070 size-full" src="https://cdn.laoshoucun.com/web/2026/03/1-1-1.jpg" alt="" width="1005" height="770" srcset="https://cdn.laoshoucun.com/web/2026/03/1-1-1.jpg 1005w, https://cdn.laoshoucun.com/web/2026/03/1-1-1-300x230.jpg 300w, https://cdn.laoshoucun.com/web/2026/03/1-1-1-768x588.jpg 768w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 1362px) 62vw, 840px" /></p>
<p><strong>第二步：打开终端/命令行</strong><br />
&#8211; 苹果Mac电脑：按键盘 `Command + 空格`，搜索“Terminal”或“终端”，回车打开命令行窗口。<br />
&#8211; Windows电脑（重点注意）：官方强烈建议使用Linux子系统。按Win键搜索“PowerShell”，右键选择“以管理员身份运行”，输入 `wsl &#8211;install` 回车，等待安装完成后重启电脑。重启后从开始菜单打开新出现的“Ubuntu”图标，这就是你的命令行窗口。</p>
<p>我这里就以mac为例，在刚才打开的代码框里输入官网复制的这行代码，然后按回车。windows的话记得切换一下</p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2071" src="https://cdn.laoshoucun.com/web/2026/03/1-2-1.jpg" alt="" width="620" height="418" srcset="https://cdn.laoshoucun.com/web/2026/03/1-2-1.jpg 620w, https://cdn.laoshoucun.com/web/2026/03/1-2-1-300x202.jpg 300w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 984px) 61vw, (max-width: 1362px) 45vw, 600px" /></p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2072" src="https://cdn.laoshoucun.com/web/2026/03/1-3-1.jpg" alt="" width="848" height="213" srcset="https://cdn.laoshoucun.com/web/2026/03/1-3-1.jpg 848w, https://cdn.laoshoucun.com/web/2026/03/1-3-1-300x75.jpg 300w, https://cdn.laoshoucun.com/web/2026/03/1-3-1-768x193.jpg 768w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 1362px) 62vw, 840px" /></p>
<p><strong>第三步：执行安装脚本</strong><br />
以Mac为例，在刚才打开的命令行里输入从官网复制的代码，按回车执行。这个脚本会自动检测你的电脑环境，缺什么补什么（连必要的Node.js运行环境都会全自动帮你下载装好），直到屏幕提示安装完成。</p>
<p><strong>第四步：唤醒配置向导</strong><br />
安装完成后，在命令行里输入唤醒命令并回车：<br />
openclaw onboard &#8211;install-daemon</p>
<p><strong>第五步：完成配置</strong><br />
屏幕上会出现交互式的中文向导提示：<br />
1. 用键盘上下键选择你要用的AI模型（比如免费的DeepSeek或通义千问）；<br />
2. 按提示扫码绑定你的微信/QQ/Telegram；<br />
3. 配置完成后，“龙虾”就会在你的电脑后台24小时常驻运行了！</p>
<p>⚠️ 小贴士：很多人说的“烧token”就发生在这一步，免费模型效果一般，好用的模型发几句话就会消耗不少费用，大家可以根据自己的需求选择。</p>

---

原文链接：[https://www.laoshoucun.com/openclawzn/2069](https://www.laoshoucun.com/openclawzn/2069)
