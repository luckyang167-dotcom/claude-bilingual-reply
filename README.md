# Claude Bilingual Reply

Claude Code 个人技能集合，专注于双语（英文-中文）输出与英文语法检查。

This repository provides personal skills for Claude Code, focusing on bilingual (English-Chinese) output and English grammar checking.

## 项目结构

```
claude-bilingual-reply/
├── README.md                  # 项目说明文档
├── CLAUDE.md                  # Claude Code 项目级指令
├── .gitignore
└── bilingual-output/
    └── SKILL.md               # bilingual-output 技能定义
```

## 技能列表

### bilingual-output

当用户希望获得英中双语回复时使用：英文在上、中文逐句翻译在下，并在作答前对用户输入的英文进行语法检查。该技能为常驻启用。

该技能的核心行为：

- **语法检查**：检查用户英文输入的拼写、用词、主谓一致、时态、冠词、介词等常见问题，以简短叙述形式给出修正，不使用表格。无英文输入时跳过此模块；无错误时提示 "Your English looks good."。
- **双语格式**：一句英文、一句中文翻译，句对之间空行分隔。代码块、行内代码、命令、路径、URL、技术标识符及引用的用户原文均不翻译。

详细的技能说明见 `bilingual-output/SKILL.md`。

## 安装与使用

将本仓库中的技能目录放置到 Claude Code 的技能加载路径下，或在全局 `~/.claude/CLAUDE.md` 中引用 `bilingual-output` 技能即可在每次会话启用双语输出。

```bash
# 克隆仓库
git clone <repo-url> claude-bilingual-reply
cd claude-bilingual-reply

# 查看技能定义
cat bilingual-output/SKILL.md
```

## 许可证

个人使用。

