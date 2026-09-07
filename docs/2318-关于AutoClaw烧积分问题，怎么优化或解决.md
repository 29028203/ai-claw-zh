# 关于AutoClaw 烧积分问题，怎么优化或解决

> 原文链接：[https://www.laoshoucun.com/autoclawzl/2318](https://www.laoshoucun.com/autoclawzl/2318)

<p>最近很多用户在使用 AutoClaw 时，核心痛点是：跑任务时系统似乎会调用所有 Skill，导致简单任务也产生不必要的积分消耗，尤其是原装 Skill 较多时，“烧积分”现象更明显。这种是什么情况呢？</p>
<p><strong>官方机制澄清</strong><br />
1. **无重复 Skill**：当前版本 <a href="/autoclaw/">AutoClaw</a> 原装 Skill 不存在功能完全重复的情况，无需担心冗余调用。<br />
2. **调用逻辑**：<br />
&#8211; 已禁用的 Skill 不会被系统调用，不产生任何积分消耗。<br />
&#8211; 未禁用的 Skill 仅会按需调用，不会在对话中无差别启动所有工具，无需担心额外消耗。</p>
<p><strong>积分优化建议</strong><br />
&#8211; 按需禁用：根据你的使用场景，在 Skill 管理界面关闭长期用不上的技能，减少无效加载。<br />
&#8211; 精准指令：任务描述尽量明确，引导系统调用对应工具，降低冗余触发概率。</p>
<p>&nbsp;</p>

---

原文链接：[https://www.laoshoucun.com/autoclawzl/2318](https://www.laoshoucun.com/autoclawzl/2318)
