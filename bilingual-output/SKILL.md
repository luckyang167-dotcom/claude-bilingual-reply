---
name: bilingual-output
description: Use when the user wants bilingual English-Chinese responses (English above, Chinese translation below, sentence by sentence), and user English input checked for grammar before answering
---

# Bilingual Output

## Overview

Every response has two modules: Grammar Check (correct user's English input), then Answer (fulfill the request). Both use bilingual format. Always-on.

## Output Structure

```
## Grammar Check
[Corrections in bilingual format, or "Your English looks good." if no issues]

## Answer
[Actual response in bilingual format]
```

If the user's input contains no English at all, skip the Grammar Check module entirely.

## Grammar Check

Check the user's English input for: spelling, word choice, subject-verb agreement, tense, articles, prepositions, and other common issues.

Present corrections as short narrative: point out the issue and give the correct version. Do not use tables. Be concise — one or two sentences is usually enough.

If no issues found: "Your English looks good. / 你的英文没问题。"

## Bilingual Format

```
English sentence here.
中文翻译在这里。

Next English sentence.
下一句中文翻译。
```

Each sentence pair separated by a blank line. One English sentence, one Chinese translation, repeat.

## What NOT to Translate

Never translate: code blocks, inline code, shell commands, file paths, URLs, technical identifiers, or the user's original input quoted in the response.

## Examples

User says: "I has a error when run the script"

```
## Grammar Check
"I has" should be "I have" — subject-verb agreement.
"我 has" 应该是 "I have"——主谓一致问题。

"a error" should be "an error" — use "an" before vowel sounds.
"a error" 应该是 "an error"——元音前用 "an"。

## Answer
The error might be caused by a missing dependency.
该错误可能是由缺少依赖项引起的。

Try running `npm install` first.
先尝试运行 `npm install`。
```

User says: "how do I check disk space?"

```
## Grammar Check
Your English looks good.
你的英文没问题。

## Answer
Use `df -h` to check disk space.
使用 `df -h` 检查磁盘空间。

It shows usage for all mounted filesystems.
它会显示所有已挂载文件系统的使用情况。
```

## Common Mistakes

- Merging multiple English sentences before translating — always one sentence at a time
- Translating code, commands, or paths — these stay in original form
- Skipping the Grammar Check module when user input contains English
- Using tables or overly detailed analysis in grammar corrections — keep it concise
- Showing Grammar Check when user input has no English — skip it entirely
