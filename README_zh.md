# Skills: 推荐系统论文写作

[English](./README.md) | [中文](./README_zh.md)

本仓库提供一个用于撰写和修改推荐系统研究论文的 Codex Skill。

该 Skill 面向 KDD、SIGIR、WWW、AAAI、ACL、RecSys、CIKM、WSDM 等会议的论文写作风格进行适配。它覆盖通用推荐系统论文写作，也覆盖 LLM-based recommendation、公平性/去偏/因果推荐、序列推荐、召回、排序以及实验部分的写作与审查。

## 致谢

本仓库中的主要写作原则与方法论受彭思达老师公开学习笔记启发：

- https://pengsida.notion.site/c1a22465a0fa4b15a12985223916048e
- 彭思达老师原始仓库：https://github.com/pengsida/learning_research

本仓库也基于并致谢以下项目：

- https://github.com/Master-cai/Research-Paper-Writing-Skills/tree/main

我的贡献主要是面向推荐系统领域进行适配、内容重构，并封装为可复用的 Skill。

## 仓库结构

当前仓库提供一个 Skill 包：

- `rs-paper-writing/`
  - `SKILL.md`：核心工作流与使用规则
  - `references/`：按章节拆分的写作指南与模板
  - `agents/openai.yaml`：Agent 元信息

常见使用场景：

- 撰写或修改 Abstract、Introduction、Preliminary、Method、Experiments、Related Work 和 Conclusion
- 改善章节逻辑、段落衔接以及面向审稿人的表达清晰度
- 检查 claim-evidence 对齐
- 审查指标、baseline、显著性、效率、LLM 生成有效性、grounding，以及公平性与准确率之间的 trade-off
- 在投稿前从推荐系统审稿人的视角进行自查

## 安装方式

以下命令默认在仓库根目录执行。

### 1. Codex

将 Skill 复制到 `$CODEX_HOME/skills/`：

```bash
mkdir -p "$CODEX_HOME/skills"
cp -R rs-paper-writing "$CODEX_HOME/skills/"
```

使用示例：

```text
Use $rs-paper-writing to improve my recommender-system paper's Introduction.
```

### 2. Claude Code

可以选择全局安装或项目级安装。

全局安装：

```bash
mkdir -p "$HOME/.claude/skills"
cp -R rs-paper-writing "$HOME/.claude/skills/"
```

项目级安装：

```bash
mkdir -p .claude/skills
cp -R rs-paper-writing .claude/skills/
```

使用时可以显式指定该 Skill，例如：

```text
Please use the rs-paper-writing skill.
```

### 3. Gemini

将该 Skill 复制到 Gemini 的 skills 目录：

```bash
mkdir -p "$HOME/.gemini/skills"
cp -R rs-paper-writing "$HOME/.gemini/skills/"
```

随后可以直接提出具体任务，例如重写 Abstract 并检查 claim-evidence 对齐。

## 许可证

本项目采用 MIT License，详见 [LICENSE](./LICENSE)。
