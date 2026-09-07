# 什么是Copaw智能体的人设，怎么配置和管理？

> 原文链接：[https://www.laoshoucun.com/copawzn/2233](https://www.laoshoucun.com/copawzn/2233)

<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2234" src="https://cdn.laoshoucun.com/web/2026/04/O1CN01IH0RKW1YhGyQLgQnH_6000000003090-2-tps-1708-954.avif" alt="" width="1708" height="954" /></p>
<p>CoPaw 通过一组 Markdown 文件定义智能体的&#8221;人设&#8221;，这些文件会被加载到系统提示词（System Prompt）中，决定智能体的行为风格、工作方式和个性特征。你可以通过编辑这些文件，让智能体成为符合你需求的专属助手——无论是严谨的工作助理、温暖的生活伙伴，还是技术专家。</p>
<p><strong>人设文件</strong><br />
CoPaw 的人设由 Markdown 文件定义，默认位于智能体工作区目录下。工作区目录的位置取决于 COPAW_WORKING_DIR 环境变量（默认为 ~/.copaw），完整路径为：$COPAW_WORKING_DIR/workspaces/{agent_id}/</p>
<p><strong>人设文件是灵活可扩展的</strong>。下面展示的是默认配置，你可以自由地添加新的 Markdown 文件或删除现有文件。只要在控制台的「Agent → Workspace」页面中启用它们，任何 Markdown 文件都能加载到系统提示词中。</p>
<p>人设文件是灵活可扩展的。下面展示的是默认配置，你可以自由地添加新的 Markdown 文件或删除现有文件。只要在控制台的「Agent → Workspace」页面中启用它们，任何 Markdown 文件都能加载到系统提示词中。</p>
<p><strong>默认人设文件</strong><br />
以下是默认配置中的人设文件（默认会被加载到系统提示词）：</p>
<p>AGENTS.md &#8211; 工作流程、规则与指南<br />
详细的操作规范和工作流程，包括记忆管理策略、安全准则、工具使用说明等。这是智能体的&#8221;操作手册&#8221;，告诉它如何完成各种任务。</p>
<p><strong>主要内容：</strong></p>
<p>记忆文件的使用方式（MEMORY.md、memory/YYYY-MM-DD.md）<br />
安全与隐私准则<br />
工具与 Skills 的使用说明<br />
心跳（Heartbeat）相关规则（如果启用）<br />
SOUL.md &#8211; 核心身份与行为原则<br />
定义智能体的价值观、风格和行为准则。这是智能体的&#8221;灵魂&#8221;，决定它的个性特征和处事方式。</p>
<p><strong>主要内容：</strong></p>
<p>核心准则（如何与用户互动）<br />
边界与底线（什么不能做）<br />
风格与语气（正式、随意、专业等）<br />
连续性说明（通过文件保持记忆）<br />
PROFILE.md &#8211; 身份信息与用户资料<br />
记录智能体的身份设定和用户的个人资料，让智能体更了解你，提供个性化服务。</p>
<p><strong>主要内容：</strong></p>
<p>身份 section：智能体的名字、定位（AI助手/机器人/其他）、风格<br />
用户资料 section：用户的名字、称呼、偏好、背景信息<br />
MEMORY.md &#8211; 长期记忆<br />
虽然 MEMORY.md 也是工作区中的重要文件，但它不会默认加载到系统提示词中。智能体在需要时可以通过 memory_search 工具主动检索记忆内容，或使用 read_file 工具读取。</p>
<p>为什么不默认加载？ 避免过多历史信息占用上下文空间。智能体会按需查询，保持系统提示词精简高效。</p>
<p>MEMORY.md 用于存储经过提炼的长期记忆（重要决策、经验教训、用户偏好等）。</p>
<p><strong>BOOTSTRAP.md &#8211; 首次引导</strong><br />
首次运行 copaw init 时会自动创建 BOOTSTRAP.md，它引导用户和智能体进行初次&#8221;对话&#8221;，共同定义身份、偏好和风格。完成引导后，智能体会将设定写入 PROFILE.md 和 SOUL.md，然后删除 BOOTSTRAP.md。</p>
<p><strong>引导内容：</strong></p>
<p>确定智能体的名字、定位、风格<br />
了解用户的基本信息<br />
讨论行为偏好和边界<br />
将内容写入对应文件后删除 BOOTSTRAP.md<br />
完成引导后，BOOTSTRAP.md 会被删除，所以它只在首次初始化时存在。</p>
<h3>配置与管理</h3>
<p>通过控制台管理<br />
在控制台的 工作区 → 文件 页面，你可以：</p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2235" src="https://cdn.laoshoucun.com/web/2026/04/O1CN01kiXTYI1IyBka8Vlqh_6000000000961-2-tps-3822-2064.avif" alt="" width="3822" height="2064" /></p>
<p>&nbsp;</p>
<p>查看所有人设文件：左侧面板列出工作区中的所有 Markdown 文件（仅显示 .md 文件）<br />
在线编辑内容：点击文件后在右侧编辑器中修改内容，点击「保存」生效<br />
启用/禁用文件：每个文件右侧有开关，控制是否加载到系统提示词<br />
已启用（开关打开，显示绿色圆点）：文件内容会加载到系统提示词<br />
已禁用（开关关闭）：文件不会加载到系统提示词<br />
调整加载顺序：启用的文件可以拖拽排序，顺序影响它们在系统提示词中的拼接顺序（从上到下依次拼接，靠前的文件会先被加载）<br />
上传/下载工作区：<br />
上传 ZIP 文件（最大 100MB）批量导入人设文件到工作区（会覆盖同名文件，非 .md 文件不会在界面显示但会被保留）<br />
下载整个工作区为 ZIP 文件进行备份<br />
查看工作区路径：页面顶部显示当前工作区的完整路径<br />
热重载： 修改人设文件后会自动生效，无需重启服务。</p>
<p>多智能体支持： 每个智能体都有独立的人设配置，互不干扰。在控制台顶部切换智能体后，看到的是该智能体的专属工作区文件。这意味着：</p>
<p>不同智能体可以有完全不同的 AGENTS.md、SOUL.md、PROFILE.md<br />
修改一个智能体的人设文件不会影响其他智能体<br />
每个智能体的人设独立演化，互不冲突</p>
<p><strong>通过配置文件管理</strong><br />
你也可以直接修改智能体配置文件（~/.copaw/workspaces/{agent_id}/agent.json）中的 system_prompt_files 字段来管理人设文件的加载：</p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2236" src="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135409_379.png" alt="" width="700" height="143" srcset="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135409_379.png 700w, https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135409_379-300x61.png 300w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 984px) 61vw, (max-width: 1362px) 45vw, 600px" /></p>
<p>数组中的文件名对应工作区目录下的 Markdown 文件<br />
数组顺序决定加载顺序<br />
留空或使用空数组时，智能体会使用默认的 &#8220;You are a helpful assistant&#8221; 提示词<br />
首次初始化<br />
运行 copaw init 时，系统会根据你选择的语言（zh / en / ru）自动创建模板文件：</p>
<p>AGENTS.md<br />
SOUL.md<br />
PROFILE.md<br />
BOOTSTRAP.md（首次引导文件）<br />
如果使用 copaw init &#8211;defaults，则默认语言为 zh（中文）。</p>
<p><strong>切换智能体语言</strong><br />
你可以在控制台的「工作区 → 运行配置」页面中切换智能体语言。切换后：</p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2237" src="https://cdn.laoshoucun.com/web/2026/04/O1CN015Q2kkH21EWybTeoED_6000000006953-2-tps-3822-2064.avif" alt="" width="3822" height="2064" /></p>
<p>系统会用新语言的模板覆盖现有的人设文件（AGENTS.md、SOUL.md、PROFILE.md）<br />
这是智能体自身的语言设置，决定系统提示词的语言<br />
与控制台界面的显示语言无关（控制台语言在右上角切换）<br />
注意：切换智能体语言会覆盖你对人设文件的自定义修改，请在切换前备份重要内容（可使用控制台的「下载」功能备份整个工作区）。</p>
<h3><strong>System Prompt 的完整内容</strong></h3>
<p>除了人设文件，系统提示词中还包含以下自动生成的内容，确保智能体正常工作：</p>
<p><strong>整体结构示意</strong></p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2238" src="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135638_145.png" alt="" width="694" height="353" srcset="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135638_145.png 694w, https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135638_145-300x153.png 300w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 984px) 61vw, (max-width: 1362px) 45vw, 600px" /></p>
<p><strong>智能体身份标识</strong></p>
<p><img loading="lazy" decoding="async" class="alignnone size-full wp-image-2239" src="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135724_005.png" alt="" width="698" height="144" srcset="https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135724_005.png 698w, https://cdn.laoshoucun.com/web/2026/04/微信图片_2026-04-02_135724_005-300x62.png 300w" sizes="auto, (max-width: 709px) 85vw, (max-width: 909px) 67vw, (max-width: 984px) 61vw, (max-width: 1362px) 45vw, 600px" /></p>
<p>在多智能体环境中，智能体需要知道自己的 ID，以便调用其他智能体或识别自己的工作区。</p>
<p>上下文信息（运行时注入）<br />
系统会在每次对话时动态注入以下信息：</p>
<p>当前时间与时区：让智能体知道现在是几点，正确处理时间相关的任务<br />
工作目录路径：智能体当前的工作区位置<br />
可用工具列表：当前启用的内置工具和 MCP 工具<br />
Skills 列表：当前启用的 Skills 及其描述<br />
这些信息不会保存在文件中，而是每次对话时根据当前状态动态生成，确保智能体始终拥有最新的环境信息。</p>
<p>工具与 Skills 的详细说明<br />
系统提示词中还包含工具和 Skills 的说明：</p>
<p>内置工具与 MCP 工具：参见 MCP 与内置工具<br />
Skills：每个启用的 Skill 会加载其 SKILL.md 的部分内容（name 和 description 字段），告诉智能体该 Skill 的用途。<br />
人设管理机制设计受 OpenClaw 启发，在此表示感谢。</p>
<p>&nbsp;</p>
<p>System Prompt 的完整内容<br />
除了人设文件，系统提示词中还包含以下自动生成的内容，确保智能体正常工作：</p>
<p>整体结构示意</p>
<p>复制<br />
[智能体身份标识]<br />
↓<br />
[人设文件内容 &#8211; 按启用顺序拼接]<br />
AGENTS.md<br />
SOUL.md<br />
PROFILE.md<br />
↓<br />
[运行时上下文信息 &#8211; 动态注入]<br />
&#8211; 当前时间与时区<br />
&#8211; 工作目录路径<br />
&#8211; 可用工具列表<br />
&#8211; Skills 列表与说明<br />
智能体身份标识</p>
<p>复制<br />
# Agent Identity</p>
<p>Your agent id is `{agent_id}`. This is your unique identifier in the multi-agent system.<br />
在多智能体环境中，智能体需要知道自己的 ID，以便调用其他智能体或识别自己的工作区。</p>
<p>上下文信息（运行时注入）<br />
系统会在每次对话时动态注入以下信息：</p>
<p>当前时间与时区：让智能体知道现在是几点，正确处理时间相关的任务<br />
工作目录路径：智能体当前的工作区位置<br />
可用工具列表：当前启用的内置工具和 MCP 工具<br />
Skills 列表：当前启用的 Skills 及其描述<br />
这些信息不会保存在文件中，而是每次对话时根据当前状态动态生成，确保智能体始终拥有最新的环境信息。</p>
<p>工具与 Skills 的详细说明<br />
系统提示词中还包含工具和 Skills 的说明：</p>
<p>内置工具与 MCP 工具：参见 MCP 与内置工具<br />
Skills：每个启用的 Skill 会加载其 SKILL.md 的部分内容（name 和 description 字段），告诉智能体该 Skill 的用途。详见 Skills<br />
人设管理机制设计受 OpenClaw 启发，在此表示感谢。</p>
<p><strong>内置 QA 智能体</strong><br />
CoPaw 在首次运行 copaw init 时会自动创建一个名为 &#8220;QA Agent&#8221; 的内置智能体（ID：CoPaw_QA_Agent_0.1beta1）。</p>
<p>QA 智能体的特点<br />
这是一个专门用于回答 CoPaw 相关问题的智能体：</p>
<p>专属人设：使用专门为问答优化的人设文件（与普通智能体不同）<br />
预装技能：自动启用 guidance 和 copaw_source_index 技能，可以查询 CoPaw 官方文档和源码<br />
工具配置：默认只启用核心工具（execute_shell_command、read_file、write_file、edit_file、view_image），其他内置工具默认禁用<br />
自动维护：每次运行 copaw init 时会自动确保该智能体存在<br />
如何使用？<br />
您可以在控制台右上角的智能体切换器中选择 &#8220;QA Agent&#8221;，然后向它提问关于 <a href="/copaw/">CoPaw</a> 的任何问题。</p>
<p>适合问什么：</p>
<p>&#8220;如何配置钉钉频道？&#8221;<br />
&#8220;记忆系统是怎么工作的？&#8221;<br />
&#8220;支持哪些 MCP 工具？&#8221;<br />
不适合做什么：</p>
<p>复杂的编程任务<br />
可以修改或删除吗？<br />
可以修改：您可以像管理其他智能体一样，在&#8221;智能体 → 工作区&#8221;中编辑它的人设文件，或在&#8221;智能体 → 技能&#8221;中调整技能和工具<br />
可以删除：在&#8221;设置 → 智能体管理&#8221;页面删除（删除后不影响其他智能体，下次 copaw init 会重新创建）<br />
工作区位置：$COPAW_WORKING_DIR/workspaces/CoPaw_QA_Agent_0.1beta1/（默认为 ~/.copaw/workspaces/CoPaw_QA_Agent_0.1beta1/）</p>

---

原文链接：[https://www.laoshoucun.com/copawzn/2233](https://www.laoshoucun.com/copawzn/2233)
