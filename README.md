# lx-skill

`lx-skill` 是一个持续生长的 AI 教育、新时代教育与数字教育 Agent Skills 技能包，由乡村教育一线实践与 AI 赋能教学经验提炼而成。它帮助 Codex、Claude Code 及其他兼容 Agent Skills 标准的智能体，更全面地理解学生、家长、教师和学校情境，并给出有依据、可执行、不过度指责的教育建议。

首发版本包含两个技能：

| Skill | 适用场景 |
| --- | --- |
| `lx-education-diagnosis` | 全局教育与亲子学习方式诊断：学习动力、成绩变化、作业拖延、手机使用、亲子冲突、课堂参与、AI学习方式等 |
| `lx-parent-learning-environment` | 家庭学习环境诊断：催促、比较、电子设备、任务模糊、难度失配、反馈过慢和家庭规则等 |

## 设计理念

- 诊断系统，不诊断人。
- 教育首先要保护并唤醒自主性、好奇心和行动能力。
- 技术和 AI 必须服务学生真实成长，而不是炫技或替代思考。
- 用可接受的表达传递有穿透力的判断，把批判翻译为建设性行动。
- 先做可逆、低成本、可观察的小实验，再根据结果迭代。
- 不进行心理或医学诊断，不使用羞辱、恐吓或标签化语言。

## 典型使用场景

- “孩子每天都要催才写作业，是不是不自律？”
- “孩子一回家就玩手机，没收手机后冲突更大，怎么办？”
- “学生上课不参与，但玩游戏时很专注，问题到底在哪里？”
- “补课越来越多，成绩和学习动力却都在下降。”
- “家长、老师和孩子的目标不一致，怎么找到真正的矛盾？”
- “怎样让 AI 成为学习陪练，而不是代写答案的工具？”

## 下载

```bash
git clone https://github.com/lxqq66/lx-skill.git
cd lx-skill
```

仓库中的每个 skill 都是独立文件夹，可以安装整个技能包，也可以只复制一个技能。

## 安装到 Codex

Codex 的个人 skills 目录是 `~/.agents/skills/`：

```bash
mkdir -p ~/.agents/skills
cp -R skills/lx-education-diagnosis ~/.agents/skills/
cp -R skills/lx-parent-learning-environment ~/.agents/skills/
```

若只希望在当前项目使用，复制到项目根目录的 `.agents/skills/`：

```bash
mkdir -p .agents/skills
cp -R skills/lx-education-diagnosis .agents/skills/
cp -R skills/lx-parent-learning-environment .agents/skills/
```

在 Codex 中可以显式调用：

```text
$lx-education-diagnosis
$lx-parent-learning-environment
```

也可以直接描述问题；当请求符合 skill 的 `description` 时，Codex 可以自动选择对应 skill。若新增的 skill 没有出现，重启 Codex。

## 安装到 Claude Code

Claude Code 的个人 skills 目录是 `~/.claude/skills/`：

```bash
mkdir -p ~/.claude/skills
cp -R skills/lx-education-diagnosis ~/.claude/skills/
cp -R skills/lx-parent-learning-environment ~/.claude/skills/
```

若只希望在当前项目使用，复制到 `.claude/skills/`：

```bash
mkdir -p .claude/skills
cp -R skills/lx-education-diagnosis .claude/skills/
cp -R skills/lx-parent-learning-environment .claude/skills/
```

在 Claude Code 中可以直接调用：

```text
/lx-education-diagnosis
/lx-parent-learning-environment
```

Claude Code 也会根据描述自动判断何时加载 skill。

## Windows PowerShell 安装示例

Codex：

```powershell
New-Item -ItemType Directory -Force "$HOME\.agents\skills"
Copy-Item -Recurse -Force ".\skills\lx-education-diagnosis" "$HOME\.agents\skills\"
Copy-Item -Recurse -Force ".\skills\lx-parent-learning-environment" "$HOME\.agents\skills\"
```

Claude Code：

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills"
Copy-Item -Recurse -Force ".\skills\lx-education-diagnosis" "$HOME\.claude\skills\"
Copy-Item -Recurse -Force ".\skills\lx-parent-learning-environment" "$HOME\.claude\skills\"
```

## 使用方式

### 全局教育诊断

```text
使用 lx-education-diagnosis。不要马上给结论，请先分轮问我必要的问题。
我的孩子五年级，最近不愿写作业，一提学习就吵架。
```

该 skill 会逐步了解孩子状态、家庭期待、学校情境、任务难度、反馈方式、手机和 AI 使用，再区分事实、可能机制与未知信息，最终给出一个七天行动实验。

### 家庭学习环境诊断

```text
使用 lx-parent-learning-environment，分析我们家的催促循环。
请一次只问两三个问题，最后帮我们制定一个七天实验。
```

该 skill 会重点检查空间诱因、任务清晰度、难度匹配、即时反馈、设备功能、家长焦虑和孩子的选择空间。

## 更新

```bash
cd lx-skill
git pull
```

更新仓库后，重新复制需要的 skill 文件夹到个人或项目 skills 目录。

## 仓库结构

```text
lx-skill/
├── README.md
├── ROADMAP.md
├── tests/evaluation-cases.md
└── skills/
    ├── lx-education-diagnosis/
    │   ├── SKILL.md
    │   ├── agents/openai.yaml
    │   └── references/
    └── lx-parent-learning-environment/
        ├── SKILL.md
        ├── agents/openai.yaml
        └── references/
```

`SKILL.md` 使用开放的 [Agent Skills 规范](https://agentskills.io/specification)。安装路径参考 [OpenAI Codex Skills 文档](https://learn.chatgpt.com/docs/build-skills) 与 [Claude Code Skills 文档](https://code.claude.com/docs/en/skills)。`agents/openai.yaml` 是 Codex 的可选界面元数据，不影响其他 Agent 读取标准 `SKILL.md`。

每次调整诊断逻辑后，可使用 [tests/evaluation-cases.md](tests/evaluation-cases.md) 中的情境做人工回归测试。

## 使用边界

本项目提供教育思考与行动实验，不替代心理、医疗、法律或紧急危机服务。涉及自伤、伤人、虐待、严重欺凌、失联或明显丧失日常功能时，应优先联系当地专业人员和紧急支持。

项目不会要求真实姓名、学校、住址或联系方式等非必要的未成年人隐私。

## 后续计划

`lx-skill` 将继续增加游戏化教学、公开课诊断、班主任助手、教师 AI 学习设计、学生 AI 学习陪练等技能。详见 [ROADMAP.md](ROADMAP.md)。
