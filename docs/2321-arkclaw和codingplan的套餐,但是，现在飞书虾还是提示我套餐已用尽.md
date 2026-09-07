# arkclaw和codingplan的套餐,但是，现在飞书虾还是提示我套餐已用尽

> 原文链接：[https://www.laoshoucun.com/arkclawzn/2321](https://www.laoshoucun.com/arkclawzn/2321)

<p>有的用户购买 ArkClaw 和 Coding Plan 套餐后，在火山引擎控制台关联已有飞书机器人（飞书虾）时，出现以下问题：<br />
1. 飞书机器人仍提示「套餐已用尽」；<br />
2. 机器人无法正常连接，无法接收/回复消息。</p>
<p><strong>分步排查方案</strong><br />
别慌~这是新旧实例切换的常见问题，按以下步骤操作即可快速解决：</p>
<p>✅ 第一步：解决飞书机器人提示「套餐用尽」问题<br />
出现该提示的核心原因是：你的飞书机器人仍绑定在旧 OpenClaw 实例上，旧实例套餐到期导致报错。<br />
1. **停掉旧实例网关，避免争抢消息**<br />
登录原来部署旧 OpenClaw 的服务器，在终端执行命令：<br />
&#8220;`bash<br />
openclaw gateway stop<br />
&#8220;`<br />
执行后，旧 OpenClaw 的网关会停止运行，不会再与新 ArkClaw 实例争抢飞书消息。<br />
2. **确认 Coding Plan 套餐状态**<br />
登录<a href="/arkclaw/">火山</a>方舟控制台，确认你购买的 Coding Plan 状态为「运行中」，确保套餐已生效。</p>
<p>✅ 第二步：核对飞书机器人配置，避免遗漏关键项<br />
按以下标准步骤逐一检查，确保 ArkClaw 与飞书开放平台的配置完全匹配：<br />
1. **飞书开放平台侧配置核对**<br />
&#8211; 权限已全量导入并审批通过；<br />
&#8211; 事件、回调的接收方式，均选择「使用长连接接收」；<br />
&#8211; 已创建版本并发布，确保配置已生效。<br />
2. **ArkClaw 侧配置核对**<br />
&#8211; 消息渠道配置页粘贴的 `App ID`、`App Secret`，与飞书开放平台的信息完全一致，无多余空格；<br />
&#8211; 提交配置并等待网关重启完成后，给飞书机器人发送任意消息获取配对码，再回到 ArkClaw 完成配对。</p>
<p>&#8212;</p>
<p>✅ 终极排查方案（仍无法连接时使用）<br />
如果完成以上步骤仍无法正常连接，可通过以下命令排查并一键修复：<br />
1. **排查飞书渠道连接状态**<br />
登录 <a href="/arkclaw/">ArkClaw</a> 终端，执行以下命令查看连接状态：<br />
&#8220;`bash<br />
openclaw channels status &#8211;probe<br />
&#8220;`<br />
2. **一键修复飞书相关配置**<br />
若提示权限缺失，直接执行以下命令自动修复：<br />
&#8220;`bash<br />
npx -y @larksuite/openclaw-lark-tools doctor &#8211;fix<br />
&#8220;`</p>
<p>⚠️ 额外场景提示<br />
如果需要将机器人部署在飞书群聊中使用，需要额外在飞书开放平台申请「获取群组中所有消息」的敏感权限，否则机器人无法接收群内消息。</p>
<p>&nbsp;</p>

---

原文链接：[https://www.laoshoucun.com/arkclawzn/2321](https://www.laoshoucun.com/arkclawzn/2321)
