# English Mastery - AI 驱动的英语学习系统

一个基于 Claude AI 的智能英语学习助手，通过**情境重构**（Contextual Reconstruction）方法帮助你高效掌握英语。

## 💡 项目理念

传统的英语学习方式是：遇到生词 → 查字典 → 记下来 → 遗忘。

**这个项目的方式是：**
- 📖 遇到不懂的句子/单词 → 向 AI 教练提问
- 🎯 AI 用**苏格拉底式教学法**引导你思考
- 📝 自动记录学习内容到日志
- 📚 生成**融合所学内容的复习文章**
- 🔄 通过阅读复习文章验证掌握情况
- ♻️ 未掌握的内容重新加入学习列表

## ✨ 核心特点

### 1. 双语教学（English-First Approach）
- **英文定义优先**：建立英语思维模式
- **中文辅助理解**：确保复杂概念清晰
- 示例：**Ephemeral** means lasting for a very short time. (短暂的，持续很短时间的)

### 2. 苏格拉底式引导
当你提问一个句子时，AI 不会直接翻译，而是：
1. 识别你的"理解障碍"（单词？词组？语法？）
2. 针对性讲解该障碍点
3. 引导你用新学到的知识再试着理解原句

### 3. 情境重构复习法
- 将每天学到的零散知识点
- 整合成一篇**连贯的英文故事**
- 通过阅读故事检验是否真正掌握
- 未掌握的内容自动重新进入学习循环

### 4. 自动化学习追踪
- 每日学习内容自动记录
- 按日期组织学习日志
- 生成定制化复习材料
- 追踪学习进度

## 📁 项目结构

```
/learn-notes/               # 每日学习记录
  2025-12-30.md            # 当天学到的单词、词组、语法
  2025-12-31.md
  ...

/review-article/           # 复习文章
  2025-12-30.md            # 基于当天学习内容生成的故事
  2025-12-31-weekly.md     # 周复习文章
  ...

CLAUDE.md                  # AI 教练的核心指令
README.md                  # 本文件
english.command            # 快速启动脚本
myrequests.md              # 项目需求文档
```

## 🚀 快速开始

### 1. 启动学习环境

**方式一：使用启动脚本**
```bash
./english.command
```

**方式二：手动启动**
```bash
cd /Users/dulei/Documents/obsidian/firsttest/CFP-Study
claude
```

### 2. 开始学习

只需要像和老师对话一样提问：

**场景 1：遇到不认识的单词**
```
你：这句话什么意思？"The ephemeral nature of social media trends..."
AI：先帮你识别生词 "ephemeral"，给出英文定义和中文解释，
    然后引导你再试着理解整个句子
```

**场景 2：不理解的语法结构**
```
你：这个句子为什么用 "were" 而不是 "was"？
    "I wish I were a bird."
AI：讲解虚拟语气（Subjunctive Mood）的用法，
    举例说明，让你造句验证理解
```

**场景 3：不熟悉的词组**
```
你："look forward to" 后面为什么加 -ing？
AI：解释 "look forward to" 中的 "to" 是介词而非不定式标记，
    演示用法，让你练习
```

### 3. 每日复习流程

#### 晚上复习（睡前）
生成当天的复习文章：
```
你：Review today
AI：读取今天的学习记录，生成一篇包含所有新学内容的故事
```

阅读生成的文章，检验掌握情况：
- ✅ **读懂了**：说明已掌握
- ❌ **没读懂**：告诉 AI 哪里不懂，AI 会重新讲解并加回今天的学习列表

#### 早晨复习（起床后）
重新阅读昨晚的复习文章，巩固记忆。

#### 周末复习
生成一周的综合复习：
```
你：Review weekend
AI：整合过去 7 天的学习内容，生成更全面的复习文章
```

## 📚 学习日志格式示例

### `/learn-notes/2025-12-31.md`
```markdown
# Learning Log: 2025-12-31

## Vocabulary / Phrases
- **Ephemeral** (adj): Lasting for a very short time. (短暂的，持续很短时间的) 
  - Context: "The beauty of the sunset was ephemeral."
- **Look forward to** (phrasal verb): To feel happy or excited about something that is going to happen. (期待，盼望) 
  - Note: Followed by -ing form.

## Grammar / Syntax
- **Subjunctive Mood** (Past): Used for hypothetical situations that are contrary to fact. (虚拟语气：用于表达与事实相反的假设情况)
  - Example: "I wish I were..." 

## Failed Review Items (Re-added)
- **Mitigate** (from 2025-12-29 review): To make something less severe, serious, or painful. (减轻，缓和)
```

### `/review-article/2025-12-31.md`
```markdown
# Review Session: 2025-12-31
**Scope**: Today's Content

## The Story: A Fleeting Moment

It was an **ephemeral** moment of pure joy. Sarah had been **looking forward to** 
this day for months. The sunset painted the sky in brilliant colors, but she knew 
this beauty would not last. She needed to **mitigate** her disappointment about 
tomorrow's early departure...

[Story continues, naturally incorporating all learned vocabulary and grammar...]

## Target List
- Ephemeral
- Look forward to
- Mitigate
- ...
```

## 🎯 学习理念

### Comprehensible Input (i+1)
- 确保每次学习都在你当前水平稍高一点的难度
- 既有挑战性又不会让你感到挫败

### Socratic Method（苏格拉底式教学）
- 不直接给答案，而是引导你思考
- 通过提问帮助你建立深层理解
- 鼓励主动思考而非被动接受

### Spaced Repetition（间隔重复）
- 当天复习（晚上）
- 次日复习（早晨）
- 周末复习（一周内容）
- 未掌握内容自动重新进入学习循环

### Context-Based Learning（情境学习）
- 不孤立记忆单词
- 在真实语境中学习和复习
- 通过故事加深记忆

## 🛠️ 常用命令

| 命令 | 功能 | 说明 |
|------|------|------|
| `Review today` | 生成今日复习文章 | 整合当天所学内容 |
| `Review weekend` / `Weekly review` | 生成周复习文章 | 整合过去 7 天内容 |
| `Check [文本]` | 分析文本并讲解 | 提交段落或句子进行学习 |

## 🔄 学习循环

```
📖 阅读 → ❓遇到困难 → 🤖 AI 讲解 → 📝 自动记录
                                        ↓
📚 生成复习文章 ← 📅 晚上/周末 ← 💡 验证掌握
        ↓
    ✅ 已掌握                ❌ 未掌握
        ↓                        ↓
    🎉 完成                ♻️ 重新学习
```

## 💪 适用场景

- 📖 **日常阅读**：读英文书籍、文章时遇到难点
- 🎬 **看视频**：观看英文视频时不理解的表达
- 💼 **工作学习**：阅读专业英文文献
- ✍️ **写作练习**：想用地道表达但不确定用法
- 🗣️ **口语准备**：学习常用口语表达和词组

## 🎓 学习建议

1. **每天坚持**：即使只学 5 个单词，也要保持学习节奏
2. **及时记录**：遇到不懂的立即提问并记录
3. **认真复习**：不要跳过晚上和早晨的复习环节
4. **诚实检验**：复习时真的不懂就说不懂，不要假装懂
5. **重视语境**：不要孤立记单词，理解它在句子中的用法

## 🌟 教学特色

### 1. 不只是翻译
- ❌ **传统方式**："ephemeral" = "短暂的"
- ✅ **AI Coach 方式**：
  - 先讲英文定义（建立英语思维）
  - 给出中文解释（确保理解）
  - 提供真实语境示例
  - 让你造句验证理解

### 2. 个性化适应
- 根据你的回答调整讲解深度
- 识别你的薄弱环节
- 提供针对性练习

### 3. 零压力环境
- 不会批判你的错误
- 鼓励式教学风格
- 营造安全的学习空间

## 📖 技术细节

### 自动化工作流
1. **学习阶段**：AI 自动将讲解的内容追加到 `/learn-notes/当天日期.md`
2. **复习生成**：根据指定时间范围读取学习记录，生成故事
3. **反馈循环**：未掌握的内容自动重新记录到当天日志

### 文件管理
- 基于日期的自动命名
- 自动创建必要的目录
- 智能追加而非覆盖已有内容

### 双语支持
- 对话可以用中文或英文
- 解释采用"英文优先，中文辅助"模式
- 复习文章用纯英文（检验理解）

## 🤝 贡献与反馈

如果你有任何建议或想法，欢迎：
- 提交 Issue
- 发起 Pull Request
- 分享你的学习心得

## 📝 开发日志

- **2025-12-31**：项目初始化，建立核心学习框架
- 基于苏格拉底式教学法设计 AI Coach 交互流程
- 实现情境重构复习方法（Contextual Reconstruction）

## 🙏 致谢

本项目受到以下理念启发：
- **Comprehensible Input Theory** (Stephen Krashen)
- **Socratic Method** (Classical Philosophy)
- **Spaced Repetition** (Cognitive Psychology)
- **Context-Based Learning** (Modern Language Teaching)

---

## 👨‍💻 关于作者

一个相信 AI 可以革新语言学习方式的探索者。

如果这个项目对你有帮助，欢迎 Star ⭐ 和分享！

**Let's Connect:**
- **LinkedIn**: [linkedin.com/in/chenran818](https://linkedin.com/in/chenran818)
- **Twitter(X)**: [x.com/chenran818](https://x.com/chenran818)
- **知乎**: [zhihu.com/people/chenran](https://www.zhihu.com/people/chenran)

---

*开始你的英语学习之旅吧！Just start by asking your first question to Claude.* 🚀
