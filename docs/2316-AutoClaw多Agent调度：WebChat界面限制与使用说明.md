# AutoClaw 多 Agent 调度：WebChat 界面限制与使用说明

> 原文链接：[https://www.laoshoucun.com/autoclawzl/2316](https://www.laoshoucun.com/autoclawzl/2316)

<p>在使用 AutoClaw对接 WebChat 界面时，我们发现了一个关键限制：WebChat 的“新对话”弹窗中，仅提供了“新对话”按钮，**没有 Agent 选择器**，无法通过 UI 直接切换已配置的 Agent。</p>
<p>需要明确的是：这并非配置问题，而是当前版本 WebChat UI 本身的功能限制。系统后台已经完成了 3 个 Agent（Oscar、Jacky、Bella）的完整配置，只是界面暂未开放切换入口。</p>
<p><strong>两种临时使用方案</strong><br />
<strong>方案一：</strong>通过 <a href="/autoclaw/">AutoClaw</a> 作为调度员（主动指令模式）<br />
你可以直接向 AutoClaw 说明需求，由它帮你调用对应 Agent 执行任务，使用示例如下：<br />
&#8211; 搜索类任务：`让 Oscar 搜一下 AI 算力热点`<br />
&#8211; 文案类任务：`让 Jacky 写一篇关于 XX 的推文`<br />
&#8211; 数据查询类任务：`让 Bella 帮我查一下数据`</p>
<p>这种方式的优势是可以精准指定执行 Agent，适合有明确分工的任务场景。</p>
<p><strong>方案二：</strong>使用默认 Agent 自动调度（被动协作模式）<br />
刷新 WebChat 页面后，新对话会默认进入 **Jacky（默认 Agent）**。Jacky 会根据你的任务需求，自动判断并调度 Oscar 和 Bella 协作完成任务，无需手动指定。</p>
<p>这种方式更贴合日常使用习惯，适合不需要刻意指定 Agent 的通用场景。</p>
<p><strong>问题总结与后续规划</strong><br />
目前的核心结论：**所有 <a href="https://www.laoshoucun.com/">Agent</a> 配置均已完成，仅 WebChat 界面暂不支持直接切换功能**。</p>
<p>当前阶段，你可以根据使用场景选择上述两种方式；后续我们也会跟进 WebChat 界面的更新，一旦 Agent 选择器功能上线，将第一时间同步使用说明。</p>
<p>如果需要测试不同 Agent 的能力，也可以直接通过方案一发起指令，验证任务执行效果。</p>
<p>&nbsp;</p>

---

原文链接：[https://www.laoshoucun.com/autoclawzl/2316](https://www.laoshoucun.com/autoclawzl/2316)
