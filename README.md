# resume-pitch-crafter 🎯

**根据岗位 JD + 你的简历，生成精简、有针对性的求职招呼语和面试自我介绍。**

每次投简历不用再对着 JD 想半天怎么介绍自己，把这件事交给 AI。

## 效果

你贴一个 JD 进来，它给你这样的输出：

> ✅ Python → 简历有：写过自动化测试脚本批量跑 200+ 用例
> ✅ 示波器/万用表 → 简历有：实习期间配合联调使用
> ⚠️ Serdes/光通信 → 无直接经验，但 STM32 通信调试经验可类比
>
> **打招呼版（90字）：**
> 熟练 Python，实习期间写过自动化测试脚本批量验证模块通信。电子信息工程专业，会用示波器/万用表排查信号问题。有 STM32 项目全流程调试经验，已拿双证，随时到岗。
>
> **面试版（180字）：**
> ...

## 安装

```bash
# 克隆到本地
git clone https://github.com/<你的用户名>/resume-pitch-crafter.git

# 创建软链接到 Claude Skills 目录
# macOS / Linux
ln -s "$(pwd)/resume-pitch-crafter" ~/.claude/skills/resume-pitch-crafter

# Windows（管理员 PowerShell）
New-Item -ItemType Junction -Path "$env:USERPROFILE\.claude\skills\resume-pitch-crafter" -Target "$pwd\resume-pitch-crafter"
```

## 使用

### 方式一：主动敲命令

```
/resume-pitch-crafter
```

然后按提示粘贴 JD，走完完整流程。

### 方式二：聊天时自动触发

当你提到以下内容时，Claude 会主动建议使用本 Skill：
- "帮我写个招呼语"
- "根据这个 JD 写自我介绍"
- "我要投简历"
- "帮我匹配一下这个岗位"
- "生成一段求职开场白"

> ⚠️ 注意：Skill 安装后不会自动运行。Claude 检测到相关话题时会建议你使用，但需要你确认才会执行完整流程。

## 核心规则

- **一句话一个点**：不说"我熟练 Python"，说"用 Python 写过批量测试脚本，自动跑 200+ 用例"
- **不说虚词**：不出现"熟练掌握""具备一定""我了解"等空话
- **不硬凑**：JD 要求的经历你没有，不编不绕，换最相关的点去打

## 文件结构

```
resume-pitch-crafter/
├── README.md       # 本文件
├── SKILL.md        # Skill 核心逻辑
└── references/     # 参考文档（后续扩展）
```

## 前提

- 你需要有一份 Markdown 格式的简历文件
- 建议把所有经历汇总到一个「主简历」文件，方便 skill 统一读取

## 许可

MIT
