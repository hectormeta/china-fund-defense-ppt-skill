# 国内基金答辩 PPT Skill

这是一个用于 Codex 的本地 Skill，用来把中文 PDF/Word 项目材料自动整理成国内基金、人才项目、重点研发、市政/省市项目等答辩 PPT，并同步生成按汇报时间分配的逐页口语讲稿。

适用场景包括：

- 国家自然科学基金青年、面上、重点项目答辩；
- 海外优青、优青、青年人才、团队项目答辩；
- 深圳、广东等地方科技项目、青年团队、产业导向项目答辩；
- 根据申请书、研究计划、简历、预算、支撑材料等生成 8-15 分钟答辩 PPT；
- 将已有 PPTX 按国内答辩风格重排、放大字号、优化逻辑和讲稿。

## 主要特点

- **国内答辩风格**：白底、深蓝结构、红色结论、汇报提纲、技术路线、预期成果、风险控制。
- **大字号现场友好**：强调 `答辩 - v3` 类型的大字模式，避免把申请书压缩成小字段落。
- **严格版式 QA**：要求对齐、文本不溢出、形状不压字、箭头不穿文字。
- **封面规范**：第一页只放项目/基金类别、项目名称、答辩人、申请代码、日期，并居中。
- **读取 PDF/Word**：从申请书、研究计划、简历、预算等材料中提取关键信息生成 PPT。
- **自动讲稿**：按总汇报时间生成每页口语讲稿，包含建议用时和转场句。

## 安装方法

### 方法一：直接克隆到 Codex skills 目录

Windows PowerShell：

```powershell
$skillDir = "$env:USERPROFILE\.codex\skills\china-fund-defense-ppt"
git clone https://github.com/hectormeta/china-fund-defense-ppt-skill.git $skillDir
```

macOS / Linux：

```bash
git clone https://github.com/hectormeta/china-fund-defense-ppt-skill.git ~/.codex/skills/china-fund-defense-ppt
```

### 方法二：下载 ZIP 手动安装

1. 在 GitHub 页面点击 `Code -> Download ZIP`。
2. 解压后，将文件夹重命名为 `china-fund-defense-ppt`。
3. 放到 Codex skills 目录：
   - Windows：`C:\Users\<你的用户名>\.codex\skills\china-fund-defense-ppt`
   - macOS/Linux：`~/.codex/skills/china-fund-defense-ppt`
4. 确认该目录下直接包含 `SKILL.md`。

## 更新方法

如果使用 git 安装：

```powershell
git -C "$env:USERPROFILE\.codex\skills\china-fund-defense-ppt" pull
```

macOS / Linux：

```bash
git -C ~/.codex/skills/china-fund-defense-ppt pull
```

## 使用示例

把申请书、研究计划或已有 PPTX 发给 Codex 后，可以这样说：

```text
使用 china-fund-defense-ppt skill，读取这个申请书，生成一个 8 分钟国内基金答辩 PPT，并生成逐页讲稿。
```

```text
把这个 PPT 改成国内基金答辩风格，字号放大，封面居中，文字不要溢出，生成 10 分钟讲稿。
```

```text
根据这份青年基金申请书生成答辩 PPT，突出科学问题、创新点、研究基础和风险控制。
```

## 输出内容

默认输出：

- 可编辑 `.pptx`；
- PNG 预览图或预览集合；
- `答辩讲稿.md`，包含每页标题、建议用时、口语讲稿和转场句；
- 简要验证结果，例如页数、占位符检查、预览检查情况。

## 设计原则

- 一页只回答一个评审关心的问题；
- 先讲国家/地方需求和科学问题，再讲方案、基础、成果和风险；
- 页面文字宁可少，不要小；
- 重点结论用红色，结构和章节用深蓝；
- 所有图形、文字、箭头必须对齐，不允许重叠；
- 讲稿必须能按时说完，而不是把页面文字念一遍。

## 目录结构

```text
china-fund-defense-ppt-skill/
├─ SKILL.md
├─ README.md
├─ LICENSE
├─ agents/
│  └─ openai.yaml
└─ references/
   ├─ document-ingestion.md
   ├─ slide-blueprints.md
   └─ style-guide.md
```

## 注意事项

- 该 skill 不包含任何私有申请材料、答辩 PPT 或个人信息。
- 生成的 PPT 内容应来自用户提供的材料；不要直接复用参考答辩中的姓名、单位、数据或未公开图片。
- 如果材料缺失，skill 会生成可用初稿并标记需要补充的信息。

## License

MIT License
