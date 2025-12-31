---
description: Stop asking and log immediately - user signals understanding
argument-hint: none
---

# Stop & Log Command - /ok

**Purpose**: 当用户说 `/ok` 时，表示"我明白了，别再问了，直接记录吧"。

## 使用场景：

### 正常对话流程：
```
用户：这个词什么意思？
AI：[开始讲解单词...]
AI：[准备问验证问题...]
用户：/ok  ← 中断信号
AI：✅ 已记录 ← 立即停止提问，直接记录
```

### 关键理解：
- `/ok` = "我懂了，不用再问我了"
- `/ok` = "把刚才讲的内容记录下来"
- `/ok` = 中断验证提问的信号

## 工作机制：

### 当用户发送 `/ok` 时：

1. **立即停止**：
   - 不再问"你能试着翻译吗？"
   - 不再问"你能造个句子吗？"
   - 不再问任何验证问题

2. **回顾刚才的对话**：
   - 识别刚才讲解的单词/词组/语法
   - 提取关键信息（定义、用法、例句）

3. **格式化并记录**：
   - 整理成标准学习笔记格式
   - 追加到 `/learn-notes/YYYY-MM-DD.md`
   - 确认已记录

4. **简短确认**：
   - "✅ 已记录到今日学习笔记"
   - 显示记录的内容
   - 完成，等待下一个问题

## 示例对话：

### Example 1: 正常使用
```
用户：这句话什么意思？"The ephemeral beauty of cherry blossoms"

AI：这句话的难点在于 ephemeral 这个词。

Ephemeral (adjective) means lasting for a very short time, 
temporary or fleeting. (短暂的、转瞬即逝的)

在这个句子中，it describes...

用户：/ok

AI：✅ 已记录到今日学习笔记 (2025-12-31.md)

记录内容：
- **Ephemeral** (adj): Lasting for a very short time, temporary. (短暂的)
  - Context: "The ephemeral beauty of cherry blossoms"
```

### Example 2: 讲解中途打断
```
用户：look forward to 后面为什么加 ing？

AI：这是因为 look forward to 中的 to 是介词...

用户：/ok

AI：✅ 已记录到今日学习笔记 (2025-12-31.md)

记录内容：
- **Look forward to** (phrasal verb): To anticipate with pleasure. (期待)
  - Note: "to" 是介词，后面接动名词 (ing形式)
```

### Example 3: 还没讲解就说 /ok
```
用户：/ok

AI：请先告诉我你想学什么内容，我讲解后你再说 /ok 来记录 😊
```

## 记录格式：

### Vocabulary:
```markdown
- **[Word]** (part of speech): [Definition]. ([中文])
  - Context: "[Original sentence]"
```

### Phrases:
```markdown
- **[Phrase]** (type): [Explanation]. ([中文])
  - Note: [Usage notes]
```

### Grammar:
```markdown
- **[Grammar Point]**: [Explanation]. ([中文])
  - Example: "[Example]"
```

## 操作指令：

When user says `/ok`:

1. **Check context**:
   - Look at the immediately preceding conversation
   - Identify what was just explained (word/phrase/grammar)
   - If nothing was explained yet, politely ask what they want to learn

2. **Extract key information**:
   - English definition/explanation
   - Chinese translation
   - Original context/sentence from user
   - Usage notes if mentioned
   - Examples if provided

3. **Format properly**:
   - Use the standard markdown format
   - Include all relevant information
   - Make it review-friendly

4. **Append to learn-notes**:
   - File: `/learn-notes/YYYY-MM-DD.md`
   - Find or create appropriate section (Vocabulary/Phrases/Grammar)
   - Append the entry
   - Do NOT overwrite existing content

5. **Confirm briefly**:
   ```
   ✅ 已记录到今日学习笔记 (YYYY-MM-DD.md)
   
   记录内容：
   [Show what was recorded]
   ```

6. **Move on**:
   - Don't ask follow-up questions
   - Wait for user's next question
   - Ready for next learning item

## ⚠️ Critical Rules:

1. `/ok` means "I understand, stop asking questions"
2. Only record what was JUST explained in the conversation
3. DO NOT ask comprehension check questions after `/ok`
4. DO NOT ask "你能造句吗？" or similar
5. Just confirm and wait for next question
6. If `/ok` is used but nothing was explained, politely ask what to record

## What /ok IS:
✅ A stop signal - "I got it, log it"
✅ A shortcut to skip verification questions
✅ An interrupt command during teaching

## What /ok is NOT:
❌ Not a command to start teaching
❌ Not a request for explanation
❌ Not used before asking questions

## Flow Comparison:

### Without /ok:
```
Q: 单词意思？
A: [讲解]
A: "你能造句吗？" ← 会问
User: [回答]
A: [反馈] → 记录
```

### With /ok:
```
Q: 单词意思？
A: [讲解]
User: /ok ← 中断
A: ✅ 记录 ← 不问直接记录
```

**Think of `/ok` as pressing the "Save" button - immediate logging without further questions.**
