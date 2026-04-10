# 图鉴.skill — Persona Skill Router That Lives in Your IDE

> **你装了 colleague.skill / nuwa.skill 之后,下一个该装什么?**

```bash
npx skills add Aar0nPB/curator-skill -g -y
```

`30+ persona skills` · `cross-author` · `MIT`

中文世界唯一的 in-IDE persona skill router — 在 Claude Code 里说话,curator 帮你跨作者发现、推荐 persona skill。

---

## 这是什么

`curator-skill` 是一个住在你 IDE 里的 persona skill 智能调度器。

- **跨作者发现**: 你装了 nuwa 后只能匹配花叔自家 14 个 dogfood persona;curator 覆盖整个跨作者生态(30+ 起,持续增长)
- **远程动态精选库**: `persona-recommendations.json` 远程版本化,老用户被持续召回
- **不抢 creator 位**: 想自己造新 persona,curator 直接 redirect 到 nuwa / colleague / yourself

---

## 7 个用户场景

| 场景 | 你说的话 | curator 给你的 |
|---|---|---|
| **入门探索** | "有什么 persona skill" | starter pack: top 8 跨类目精选 |
| **借脑思考** | "Naval / 芒格会怎么想" | 单 persona 精准定位 |
| **方法论学习** | "想学 Karpathy 的 ML 思维" | 领域 mentor skill |
| **决策辅助** | "该不该 X / 要不要 X / 帮我想清楚" | 匹配决策类型最相关的单 persona |
| **关系延续** | "我前任 / 我导师 / 我妈" | 情感场景: 先共情,再轻推荐 |
| **自我对话** | "和未来的我对话 / 另一个我" | yourself.skill / 数字人生 |
| **角色扮演** | "想跟马斯克聊天" | nuwa 对应 dogfood |
| **创作引导** | "我想自己做一个 X 的 skill" | **直接 redirect 到 nuwa,不抢位** |

---

## 与生态其他项目的关系

| | nuwa | colleague | dot-skill | ai-skill | **curator** |
|---|---|---|---|---|---|
| 跨作者匹配 | ✗ 只 14 自家 | ✗ creator | ✓ web | ✓ 通用 | **✓ persona 专精** |
| 决策类 persona 推荐 | ✗ | ✗ | ✗ | ✗ | **✓** |
| In-IDE 主动触发 | ✓ | ✓ | ✗ web | ✓ | **✓** |
| 远程动态精选库 | ✗ | ✗ | web | ✓ | **✓** |
| 专精 persona 场景 | ✓ creator | ✓ creator | ✓ list | ✗ 通用 | **✓ router** |

**curator 不重复造轮子** — 它占的是当前生态唯一的"installable in-IDE persona-specialized router"空白生态位:

- 想**蒸馏新 persona** → 用 [nuwa](https://github.com/alchaincyf/nuwa-skill)
- 想**做同事/朋友角色** → 用 [colleague](https://github.com/titanwings/colleague-skill)
- 想在 **web 上看生态全貌** → 用 [dot-skill](https://github.com/titanwings/colleague-skill)
- 想**通用 skill 发现** → 用 [ai-skill](https://github.com/1-SKILL/ai-skill)
- 想在 **IDE 里被动地、按意图、跨作者地发现 + 推荐 persona** → **curator**(本项目)

---

## v1 收录

**30 个精选 persona**

### 思想家 Perspective(17)
Naval Ravikant · Charlie Munger · Nassim Taleb · Paul Graham · Andrej Karpathy · Ilya Sutskever · Richard Feynman · MrBeast · Steve Jobs · Elon Musk · Donald Trump · 张一鸣 · 张雪峰 · 户晨风 · 巴菲特 · 毛选 · 求是

### 关系延续 Relationship(10)
同事(titanwings) · 前任(titanwings) · 前任(小蛮) · 暗恋对象 · 父母 · 师兄 · 导师 · 老板 · 永生 · 重逢

### 自我对话 Self(3)
自己 · 永生 · 数字人生

完整列表见 [`persona-recommendations.json`](./persona-recommendations.json)。

---

## 安装

```bash
npx skills add Aar0nPB/curator-skill -g -y
```

安装后,在 Claude Code 里直接说话即可触发,例如:

```
"有什么 persona skill"
"该不该接这个 offer,帮我想清楚"
"Naval 会怎么想这个"
"我前任突然找我"
```

---

## Runtime 兼容性

`npx skills add` 协议会自动把 curator-skill install 到 **12+ 个 agent runtime** 的标准路径:

- **自动 install**: Claude Code · Cursor · Codex CLI · Gemini CLI · OpenCode · Antigravity · Kiro CLI · Trae · OpenClaw 等
- **主要验证**: Claude Code(所有 prompt 行为在此 runtime 测试)
- **为什么跨 runtime 能 work**: SKILL.md + JSON 是纯文本,在任何支持 SKILL 协议的 runtime 都能 work,不依赖任何 runtime-specific 黑科技

---

## 明确不做(防 scope creep)

- ❌ **不做 creator** — 用户想做新 persona 时 redirect 到 nuwa
- ❌ **不做 web hub** — dot-skill 已经做了
- ❌ **不做静态 markdown list** — xixu-me / tmstack 已经做了
- ❌ **不维护 persona 内容** — 只做发现/匹配/路由,内容由原作者负责
- ❌ **不做 install 之外的 social 功能**(评分、评论、社交)
- ❌ **不写复杂 Python 后端** — SKILL.md + 一个 JSON 即可

---

## 致谢

curator-skill 站在中文 persona skill 生态的肩膀上。没有以下作者的工作,curator 不会存在:

- **[titanwings](https://github.com/titanwings)** — `colleague-skill` (9.3k⭐) 开创了整个赛道,`dot-skill` 是 ecosystem 的 web hub
- **[alchaincyf 花叔](https://github.com/alchaincyf)** — `nuwa-skill` (4.1k⭐) + 14 个 dogfood persona 是 curator 收录的核心内容
- **[1-SKILL](https://github.com/1-SKILL)** — `ai-skill` 是 in-IDE meta-router 模式的灵感来源
- **[notdog1998](https://github.com/notdog1998)** — `yourself-skill` 自我蒸馏的代表作
- **[xiaoheizi8](https://github.com/xiaoheizi8)** — `crush-skills` / `parents-skills` 情感场景代表
- **[therealXiaomanChu](https://github.com/therealXiaomanChu)** — `ex-skill` 重要单 persona 作者
- **[agenmod](https://github.com/agenmod)** — `immortal-skill` 多 runtime 兼容的最佳实践
- **[xixu-me](https://github.com/xixu-me) / [tmstack](https://github.com/tmstack) / [codeman008](https://github.com/codeman008)** — 三个 awesome list 提供了完整的生态 inventory

---

## 贡献

想推荐新的 persona skill 入选 curator 的精选库?请提 [GitHub Issue](https://github.com/Aar0nPB/curator-skill/issues),包含以下信息:

- repo URL
- 中文名 + 一句话描述
- 你认为它属于哪个 scenario(8 个之一)
- 它的核心镜片(core_lens) + 局限(limits)
- (可选) 一个真实的使用示例

精选库每周 review 一次,版本号在 `_meta.version`。

---

## License

[MIT](./LICENSE)

---

# 图鉴.skill — Persona Skill Router That Lives in Your IDE (English)

> **You've installed colleague.skill / nuwa.skill — what's next?**

```bash
npx skills add Aar0nPB/curator-skill -g -y
```

`30+ persona skills` · `cross-author` · `MIT`

The only in-IDE persona skill router for the Chinese AI ecosystem — speak in Claude Code, and curator finds and recommends persona skills across authors.

## What it is

- **Cross-author discovery**: nuwa only matches its author's own 14 dogfood personas; curator covers the entire cross-author ecosystem (30+ and growing)
- **Remote dynamic curation**: `persona-recommendations.json` is versioned and updated weekly
- **Doesn't compete with creators**: if you want to distill a new persona, curator redirects you to nuwa / colleague / yourself

## How it differs

| | nuwa | colleague | dot-skill | ai-skill | **curator** |
|---|---|---|---|---|---|
| Cross-author | ✗ 14 dogfood only | ✗ creator | ✓ web | ✓ generic | **✓ persona-specialized** |
| Decision persona matching | ✗ | ✗ | ✗ | ✗ | **✓** |
| In-IDE active trigger | ✓ | ✓ | ✗ web | ✓ | **✓** |
| Remote dynamic curation | ✗ | ✗ | web | ✓ | **✓** |
| Persona-specialized | ✓ creator | ✓ creator | ✓ list | ✗ generic | **✓ router** |

## Install

```bash
npx skills add Aar0nPB/curator-skill -g -y
```

Then in Claude Code, say things like:

```
"What persona skills are out there?"
"Help me think through whether to take this offer from multiple angles"
"What would Naval think about X?"
"My ex just reached out and I don't know what to do"
```

## Runtime support

The `npx skills add` protocol auto-installs curator-skill to **12+ agent runtimes**:

- **Auto-installed to**: Claude Code · Cursor · Codex CLI · Gemini CLI · OpenCode · Antigravity · Kiro CLI · Trae · OpenClaw
- **Primary validation**: Claude Code (all prompt behaviors tested here)
- **Why it works cross-runtime**: SKILL.md + JSON is plain text, works in any SKILL-protocol-compatible runtime — no runtime-specific magic required.

## License

[MIT](./LICENSE)
