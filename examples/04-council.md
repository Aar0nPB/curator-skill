# Example 04 — 顾问团组合召唤(核心独家功能)

> 这是 curator-skill 的 viral hook 功能。当前没有任何项目做"多 persona 顾问团组合召唤"。
>
> v1 是**轻量版**: curator 帮你 orchestrate prompt + 给依次召唤脚本。Phase 2 会有 subagent 真正同时召唤。

---

## 场景 1: 创业 offer 决策(Founder Council)

```
你: 我现在在一个 5 人的早期 startup,刚收到字节的 staff offer。要不要从这个 startup 跳过去?
   帮我多角度想清楚。

curator: 你的需求是要从多个互补视角想清楚一个重大职业决策。我建议召唤【创业顾问团】:

  ### 创业顾问团 (Founder Council)
  这个决策需要 4 个互补视角。先一次性装好:

  npx skills add alchaincyf/paul-graham-skill -g -y
  npx skills add alchaincyf/steve-jobs-skill -g -y
  npx skills add alchaincyf/zhang-yiming-skill -g -y
  npx skills add alchaincyf/elon-musk-skill -g -y

  装完后,把你的决策依次贴到 4 个 prompt:

  1) 用 PG 视角:
     "我现在在 5 人 startup,收到字节 staff offer。从 PG 的角度看:
      我现在的 startup 是不是 ramen profitable?用户是不是 desperately 想要我们的产品?
      跳过去后,我会失去什么不可逆的东西?有没有 schlep blindness?"

  2) 用乔布斯视角:
     "我收到字节 staff offer。从乔布斯的角度看:
      字节 staff 是让我做'自己想做的事'还是'别人想做的事'?
      在字节,我能 say no to 的事情多不多?
      如果只能保留一件事,我会选择留在 startup 还是去字节?"

  3) 用张一鸣视角:
     "我收到字节 staff offer。从张一鸣的角度看:
      字节的'Context Not Control'文化和我现在 startup 的工作风格匹配吗?
      Staff 上面的天花板在哪?
      平庸有重力——我去字节,逃逸速度够不够?"

  4) 用马斯克视角:
     "我收到字节 staff offer。从马斯克的角度看,用第一性原理拆解:
      这两条路的真实成本是什么?(时间 + 期权 + 自由度 + 学习曲线)
      字节 staff 给我的'白痴指数'是多少?
      能不能砍掉 80% 的中间步骤,直接拿到我想要的东西?"

  4 个视角都看完,你会发现他们经常吵架——这才是顾问团的价值,逼你看到自己的盲区。
  
  ⚠️ 这是顾问团 lite 版,curator 帮你 orchestrate prompt。Phase 2 会有 subagent 真正同时召唤。
```

---

## 场景 2: 重大投资决策(Investment Council)

```
你: 我手里有 200 万,要不要 all in 一个新兴的 AI infra 公司的早期投资?

curator: 重大资产配置 + 风险评估,我建议召唤【投资顾问团】:

  ### 投资顾问团 (Investment Council)
  4 个互补视角,先一次性装好:

  npx skills add alchaincyf/munger-skill -g -y
  npx skills add alchaincyf/naval-skill -g -y
  npx skills add alchaincyf/taleb-skill -g -y
  npx skills add will2025btc/buffett-perspective -g -y

  装完后,把这个决策依次贴到 4 个 prompt:

  1) 用 Munger 视角:
     "我要 all in 200 万到 AI infra 早期投资。从 Munger 的角度,逆向思考:
      这个决策有哪些 mental model 会被违反?
      有没有被过度乐观偏误 / 社会认同 / FOMO 影响?
      '反过来想'——如果这笔投资在 2 年后归零,我会因为什么后悔?"

  2) 用 Buffett 视角:
     "AI infra 早期投资在我的能力圈里吗?
      这家公司有护城河吗?(技术 / 品牌 / 网络效应 / 成本)
      即使我看好这个 thesis,我现在的安全边际够吗?"

  3) 用 Naval 视角:
     "AI infra 是 specific knowledge 还是热门赛道的随机表演?
      这是杠杆机会(单次决策长期复利)还是 noise(频繁交易)?
      我能不能只用闲钱,长期持有 10 年?"

  4) 用 Taleb 视角:
     "all in 200 万 = 集中风险。从 Taleb 角度,这是凸的还是凹的?
      最坏情况(归零),我会被毁掉吗?
      有没有杠铃策略可以替代?(比如 90% 安全资产 + 10% 早期赌注)"

  4 个视角看完,你会发现 Munger 和 Naval 经常在吵——一个让你避免愚蠢,
  一个让你 bet on yourself。这种张力本身就是答案。

  ⚠️ 这是顾问团 lite 版。
```

---

## 场景 3: 复杂个人决策(Decision Council)

```
你: 我 35 岁,稳定大厂工程师,在考虑要不要去读个计算机的 PhD。怎么决定?

curator: 复杂人生决策,且后果不可逆——召唤【决策顾问团】:

  ### 决策顾问团 (Decision Council)
  4 个角度,不一定都同意,但能让你看清自己:

  npx skills add alchaincyf/munger-skill -g -y
  npx skills add alchaincyf/feynman-skill -g -y
  npx skills add alchaincyf/taleb-skill -g -y
  npx skills add alchaincyf/naval-skill -g -y

  装完后:

  1) 用 Munger 视角:
     "我 35 岁要不要读 PhD?逆向想——
      什么决策会让我 50 岁的时候后悔一辈子?
      把这些先排除掉,剩下的是什么?"

  2) 用 Feynman 视角:
     "我说我'想读 PhD',但我是真的想做 research,
      还是只是给'逃避当前工作'起了一个高级的名字?
      我能不能解释清楚我要研究的具体问题?
      还是只是想要那个 'PhD' 头衔?"

  3) 用 Taleb 视角:
     "35 岁读 PhD 是凸的还是凹的?
      如果错了(读完发现不喜欢 / 找不到工作),我损失什么?
      如果对了,上行空间有多大?"

  4) 用 Naval 视角:
     "PhD 的 5 年里,我能 build 什么 specific knowledge?
      读完之后,我有没有更接近'无需许可的路径'?
      还是只是把自己进一步绑死在学术体系里?"

  这 4 个视角不会给你答案——它们会让你变成那个能回答自己的人。

  ⚠️ 这是顾问团 lite 版。
```

---

## 顾问团 lite vs Phase 2 pro 的区别

| | v1 lite (现在) | Phase 2 pro (未来) |
|---|---|---|
| 实现方式 | curator 给依次召唤脚本,你手动 prompt 每个 persona | curator 用 subagent 同时召唤 N 个 persona |
| 速度 | 慢(你要一个一个贴 prompt) | 快(并行) |
| 跨 runtime | ✓ 任何 runtime 都能跑 | ✗ Claude Code only |
| 语义对齐 | 完全(你看到每个 persona 的全部输出) | 完全(subagent 隔离上下文) |
| 体验 | 像 orchestrator 给你菜单 + 配方 | 像真的有 4 个人在房间里 |

**为什么 v1 选 lite**: ddl 紧 + 跨 runtime + 不需要 subagent 黑科技就能 ship。Phase 2 再 ship "顾问团 pro" 作为下一个宣传节点。
