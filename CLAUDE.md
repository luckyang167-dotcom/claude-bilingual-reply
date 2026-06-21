# CLAUDE.md

本文件为 Claude Code 在 `claude-bilingual-reply` 项目下工作时的项目级指令。

## 项目概述

`claude-bilingual-reply` 是一个 Claude Code 个人技能集合仓库，目前包含一个技能 `bilingual-output`，用于在每次回复时输出英中双语内容并对用户英文输入进行语法检查。

## 强制指令

**在每次会话及每一轮对话开始时，必须先调用 `bilingual-output` 技能，再作答。** 不要以“这是一个简单回复”为由跳过。这是对所有其他行为的强制性覆盖，无例外。

## 目录约定

- `bilingual-output/SKILL.md`：技能定义文件，包含技能的触发条件、输出结构与示例。修改技能行为时应编辑此文件。
- `README.md`：项目说明文档。
- `.gitignore`：当前仅忽略 `.DS_Store`。

## 技能行为要点（摘要）

- 输出结构：`## Grammar Check`（语法检查，仅当用户输入含英文时出现）+ `## Answer`（正式双语回复）。
- 双语格式：一句英文、一句中文翻译，句对间空行分隔。
- 不翻译对象：代码块、行内代码、命令、路径、URL、技术标识符、引用的用户原文。
- 语法修正以简短叙述呈现，不用表格；无错误时输出 "Your English looks good."

完整说明见 `bilingual-output/SKILL.md`。

## 工作约定

- 修改技能定义后，保持 SKILL.md 的 YAML frontmatter（`name`、`description`）与正文格式不变。
- 提交信息使用 Conventional Commits 规范（如 `feat:`、`docs:`、`fix:`）。
