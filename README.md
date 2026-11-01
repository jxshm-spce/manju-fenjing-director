<p align="center">
  <img src="docs/assets/hero.png" alt="漫剧分镜提示词导演：从剧本到分镜，让每一镜接得上。支持中文时间轴、人物调度与连续性控制。" width="100%">
</p>

<h1 align="center">manju-fenjing-director<br>漫剧分镜提示词导演</h1>

<p align="center">
  把剧本里的动作、对白与情绪，写成有时间、有站位、能衔接的中文视频提示词。
</p>

<p align="center">
  <img src="docs/assets/badges.svg" alt="Skill v1.0.0 · 中文输出 · 2.0 每段 ≤15秒 · 2.5 每段 ≤30秒" width="624">
</p>

<p align="center">
  <a href="https://github.com/jxshm-spce/manju-fenjing-director/raw/refs/heads/main/dist/manju-fenjing-director-1.0.0.zip"><b>⬇ 下载技能安装包</b></a>
  &nbsp; · &nbsp;
  <a href="#quick-start">快速上手</a>
  &nbsp; · &nbsp;
  <a href="#example">看输出示例</a>
  &nbsp; · &nbsp;
  <a href="docs/usage.md">详细使用指南</a>
</p>

---

## 让镜头写得清楚，也接得自然

你已经有了剧本，接下来要解决的是：**这一段拍什么、人物站哪里、什么时候说话、结尾怎样接到下一段。**

这个 Skill 面向 AI 漫剧、短剧和剧情类视频的提示词制作。它会把剧本或现有分镜，整理成按时间展开的中文提示词，并把构图、表演、道具、光线和声音落实到具体镜头里。

适合直接交来一场戏，也适合逐段细化已有分镜。已有的台词、角色设定、素材标签和指定画风会作为创作依据。

<table>
<tr>
<td width="50%" valign="top">
<h3>⏱ 分段有边界</h3>
<p>先确认 2.0 或 2.5，再按每段 15／30 秒的上限安排动作和对白。停顿、切镜和尾镜都计入时长。</p>
</td>
<td width="50%" valign="top">
<h3>🎬 段尾能接续</h3>
<p>优先用交代人物位置的大远景，或状态明确的特写收尾；下一段写清实际承接状态。</p>
</td>
</tr>
<tr>
<td valign="top">
<h3>↔ 人物有位置</h3>
<p>写清左右、前后、朝向、视线和距离。两人同框时，按剧情选择过肩、纵深错位或侧向远景等构图。</p>
</td>
<td valign="top">
<h3>✦ 表演有动作</h3>
<p>把紧张、犹豫、试探写成停顿、目光、手部动作和听者反应，同时照顾持物手与接触关系。</p>
</td>
</tr>
</table>

<a id="quick-start"></a>

## 三步开始使用

### ① 选择一种方式交给智能体

**方式 A · 下载安装包，直接扔给智能体**

点击 **[下载技能安装包 · v1.0.0](https://github.com/jxshm-spce/manju-fenjing-director/raw/refs/heads/main/dist/manju-fenjing-director-1.0.0.zip)**，把 ZIP 文件拖进智能体对话，然后发送：

```text
请安装并使用附件中的“漫剧分镜提示词导演”Skill。
读取 SKILL.md 和 references/output-format.md，按当前平台的技能机制安装或载入。
如果这里只支持在本次对话中读取使用，请明确说明。
```

**方式 B · 在智能体中引用 GitHub 项目地址**

复制下面这段，直接发给能够访问 GitHub 的智能体：

```text
请从这个 GitHub 项目读取并使用“漫剧分镜提示词导演”：
https://github.com/jxshm-spce/manju-fenjing-director

先读取根目录的 SKILL.md 和 references/output-format.md，
按当前平台支持的方式安装或载入，然后按技能规则处理我接下来提供的剧本。
```

> 不同智能体的文件读取、联网和安装能力不同。支持技能导入的工具也可以直接导入 ZIP；需要手动放置文件时，见[详细指南](docs/usage.md#manual-install)。

### ② 发送剧本与已有资料

```text
使用“漫剧分镜提示词导演”，把下面这场戏转成中文时间轴视频提示词。
保留原台词与剧情，注意人物站位、道具状态和片段之间的衔接。

【剧本】
粘贴你的剧本或已有分镜。

【已有资料，可选】
角色档案、参考图及对应标签、场景设定、画风、画幅或特殊镜头要求。
```

### ③ 确认版本，开始生成

当前项目尚未选版本时，智能体会先问：

> 这次使用 2.0（每段不超过 15 秒）还是 2.5（每段不超过 30 秒）？

回复 `用 2.0` 或 `用 2.5` 即可。你也可以在最初的请求里直接写明。同一项目会沿用已选版本，后面可以随时改选。

| 本次选择 | 每个生成片段 | 分段方式 |
| :--- | :--- | :--- |
| **2.0** | **≤ 15 秒** | 在句末、动作落定或反应完成处自然切段 |
| **2.5** | **≤ 30 秒** | 可以承载更长的动作与对白，仍按节奏安排 |

**上限不是必须填满的长度。** 每个生成片段可以包含多个时间段与子镜头；总长超出上限时会拆段。这里的 15／30 秒是本 Skill 的制作规则，实际生成时仍需匹配所用平台的设置。

<a id="example"></a>

## 输出是什么样的？

每个时间段都按固定栏目展开，让站位、镜头、表演与对白出现在同一条时间线上：

**时间 → 时段环境 → 景别 → 镜头类型 → 人物站位与镜头 → 画面描述 → 节奏锚点 → 台词**

需要时，在台词之后增加声音说明；每个生成片段末尾给出实际时长。

下面是原创演示《旧信》中的一个 **4 秒时间段**，用于展示栏目与写法。它属于一个 12 秒的生成片段。

```text
时间：00:08-00:12
时段环境：夜，旧书店室内；东侧窗外的冷光与桌灯暖光保持稳定。
景别：手部与信封特写
镜头类型：硬切至固定特写
人物站位与镜头：
【镜头一・信封停住】00:08-00:12：摄影机位于书桌南侧，
俯拍桌面；林夏的右手从画面左侧将未封口的信封向右推至桌沿，
指尖停在信封左边缘；陈舟尚未伸手入画。
画面描述：信封沿木纹滑动后停稳，封口朝北，纸角保持平整；
最后一秒保留右手与信封的稳定接触状态，供下一段切入。
节奏锚点：推信封 → 停稳 → 留出切点。
台词：无台词。
```

**[查看《旧信》的原始剧本、两个完整片段及衔接说明 →](docs/example.md)**

演示包含 2.0 下的两个 12 秒片段，展示如何保留原台词、用特写接续手部动作，再用大远景交代人物位置。示例用于说明文本交付格式，未附实际生成视频。

## 在你的制作流程里怎么用

<img src="docs/assets/workflow.png" alt="制作流程：准备剧本与资料 → 确认2.0或2.5 → 生成时间轴提示词 → 检查衔接并进入视频制作" width="100%">

| 你现在有什么 | 可以让它做什么 |
| :--- | :--- |
| 一份已经写好的剧本 | 拆分生成片段，安排时间、镜头、动作和对白 |
| 一套已有分镜 | 保留编号与剧情，细化首帧、机位、站位和表演 |
| 一版需要调整的提示词 | 按你指出的问题修改，如持物手、视线、光向或尾镜 |
| 已经生成的前一段素材 | 根据你提供的尾帧或状态描述，安排下一段开头 |

**有配套 Skill 时可以一起使用：** 前期拿到剧本，先用 `character-acting-profile` 建立角色档案；制作角色与场景参考图时用 `lira-image-prompts`；写当前镜头时由本 Skill 组织视频提示词，并结合 `acting-system` 落实逐镜表演。

这些配套技能需要另行提供，**本仓库只包含“漫剧分镜提示词导演”**。没有配套技能或完整档案时，也可以依据已提供的剧本完成分镜提示词。

## 几条会影响成片的规则

| 关注点 | 具体做法 |
| :--- | :--- |
| **原剧本** | 保留剧情和原台词；不为塞进时长而擅自删词、改词或异常加速 |
| **双人构图** | 默认避开双人中景；保留必要互动，以过肩、纵深和单人反应等组织镜头 |
| **段尾衔接** | 优先大远景或可匹配的特写；尾镜计入总时长，下一段写出具体状态 |
| **参考素材** | 原样保留有效 `@标签`，只使用当前镜头需要的角色、场景与道具 |
| **画面连续性** | 保持持物手、道具朝向、视线、动作方向、光线和人物位置可接续 |
| **用户指定** | 明确提出的一镜到底、固定机位、结束方式或其他交付格式优先 |

<a id="faq"></a>

## 常见问题

<details>
<summary><b>它会直接生成视频吗？</b></summary>

它生成中文视频提示词。完成后，把每个生成片段交给你使用的视频生成工具，并设置相应的时长、画幅和参考素材。本仓库不包含视频生成接口或账号凭证。

</details>

<details>
<summary><b>只有故事大纲，还没有剧本怎么办？</b></summary>

建议先让智能体把大纲整理成有动作与对白的剧本，再交给这个 Skill。它最适合接手已经明确的剧情。若希望它同时扩写故事，请在请求里写清允许改编的范围。

</details>

<details>
<summary><b>为什么先问 2.0／2.5？技能版本 1.0.0 又是什么？</b></summary>

2.0／2.5 是本次制作所选的视频版本，决定按 15 秒还是 30 秒上限切段；1.0.0 是这个 Skill 安装包自身的版本号。两者含义不同。

</details>

<details>
<summary><b>双人同框还能用吗？每个镜头都要远景或特写吗？</b></summary>

可以两人同框，默认避开的是双人中景及等价的平均分配式半身构图。大远景／特写的收尾偏好针对整个生成片段的最后一镜，不要求每个小时间段都这样结束。你明确指定的特殊镜头要求优先。

</details>

<details>
<summary><b>导入后没有识别，或者提示缺少字段怎么办？</b></summary>

优先下载上方的专用 ZIP，解压后应看到 `manju-fenjing-director/SKILL.md`。该文件已包含 `version`、`name`、`display_name`、`display_name_en`、`description_zh` 和 `description_en`。不同平台的导入规范可能有差别，可把完整报错交给智能体核对，或通过 [Issues](https://github.com/jxshm-spce/manju-fenjing-director/issues) 反馈。

</details>

## 文件与进一步阅读

| 文件 | 用途 |
| :--- | :--- |
| [SKILL.md](SKILL.md) | 智能体读取的核心导演规则 |
| [references/output-format.md](references/output-format.md) | 完整时间轴交付模板 |
| [agents/openai.yaml](agents/openai.yaml) | 技能名称、简介与默认调用提示 |
| [docs/usage.md](docs/usage.md) | 安装、调用和材料准备指南 |
| [docs/example.md](docs/example.md) | 《旧信》完整文本示例 |
| [dist/manju-fenjing-director-1.0.0.zip](dist/manju-fenjing-director-1.0.0.zip) | 可下载的专用技能包 |

<details>
<summary>本页的排版参考</summary>

参考了 [Awesome Agent Skills](https://github.com/VoltAgent/awesome-agent-skills) 的封面与导航层级、[Superpowers](https://github.com/obra/superpowers) 的安装和使用组织方式，以及 [cine-director](https://github.com/socramsea/cine-director) 用完整示例解释交付物的方式。本项目的文字、演示剧本与封面图另行制作。

</details>

---

<p align="center">
  <b>先把这一镜拍清楚，再让下一镜接得上。</b><br>
  <a href="#quick-start">开始使用</a> · <a href="docs/example.md">阅读示例</a> · <a href="https://github.com/jxshm-spce/manju-fenjing-director/issues">反馈问题</a>
</p>
