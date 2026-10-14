# 贡献指南

感谢你考虑为 FDE Handbook 做出贡献！🎉

本文档会指导你如何参与本项目，让我们的内容变得更好。

---

## 📋 目录

- [行为准则](#-行为准则)
- [我能贡献什么](#-我能贡献什么)
- [如何贡献](#-如何贡献)
- [内容规范](#-内容规范)
- [提交规范](#-提交规范)
- [审稿流程](#-审稿流程)

---

## 🤝 行为准则

参与本项目即表示你同意：

- ✅ 尊重所有贡献者，不分背景、经验、性别
- ✅ 建设性反馈，对事不对人
- ✅ 聚焦于让内容更好
- ❌ 禁止人身攻击、歧视、骚扰
- ❌ 禁止发布广告、垃圾信息

违反行为准则的贡献将被拒绝，已有的贡献可能被回退。

---

## 💡 我能贡献什么？

### 优先级 1：纠错勘误

- 错别字、语法错误
- 链接失效
- 代码示例无法运行
- 过时的技术信息
- 错误的薪资数据 / 公司信息

### 优先级 2：内容补充

- 缺失的知识点
- 更清晰的解释
- 更多的代码示例
- 实战案例补充（特别欢迎金融/政企/医疗/法律行业）
- FDE 踩坑经历分享

### 优先级 3：内容创作

- 全新章节
- 全新行业 Know-how
- 全新工具横评
- 全新实战案例
- 翻译英文版（未来）

### 优先级 4：项目改进

- 改进 README
- 改进目录结构
- 编写自动化工具
- 改进 CI/CD

---

## 🚀 如何贡献

### 方式 1：GitHub PR（推荐）

适合：会使用 Git 的贡献者

```bash
# 1. Fork 本仓库
# 在 GitHub 上点击 Fork 按钮

# 2. 克隆你的 Fork
git clone https://github.com/your-username/Lumen-AI-FDE-HandBook.git
cd Lumen-AI-FDE-HandBook

# 3. 创建特性分支
git checkout -b fix/typo-in-2.1.2
# 或
git checkout -b feat/add-medical-case

# 4. 修改内容
# 编辑相关 .md 文件

# 5. 提交
git add .
git commit -m "docs: 修正 2.1.2 中 ColBERT 章节一处笔误"

# 6. 推送到你的 Fork
git push origin fix/typo-in-2.1.2

# 7. 在 GitHub 上创建 Pull Request
```

### 方式 2：GitHub Issue

适合：不会用 Git，或只想提建议

1. 在 [Issues](https://github.com/leiak/Lumen-AI-FDE-HandBook/issues) 提单
2. 选择合适的模板
3. 详细描述问题或建议

### 方式 3：GitHub Discussions

适合：开放性讨论、问答、经验分享

1. 进入 [Discussions](https://github.com/leiak/Lumen-AI-FDE-HandBook/discussions)
2. 选择分类（提问、分享、讨论等）
3. 开启话题

---

## 📐 内容规范

### 文件结构

每个章节遵循统一结构：

```markdown
# 章节标题

> 本章适合谁：...
> 学完能掌握：...
> 预计阅读：X min
> 版本：v1.X / YYYY-MM-DD

---

## 一、...

## 二、...

...

## 延伸阅读
- [相关章节](./xxx.md)

---

**本章状态**：✅/🚧/📝 ...
```

### 写作规范

#### 1. 标题层级

- `#`：仅用于章节标题（每个文件 1 个）
- `##`：一级章节
- `###`：二级章节
- `####`：尽量避免，超过 3 层会重新组织结构

#### 2. 中文 / 英文

- 中文为主，技术名词后括号标注英文
- 示例：向量数据库（Vector Database）
- 首次出现的英文缩写需展开

#### 3. 代码示例

```python
# 标题要说明意图
# 示例 1：基础 RAG 检索
def basic_rag_search(query: str, top_k: int = 5) -> list:
    """
    基础 RAG 检索流程
    Args:
        query: 用户查询
        top_k: 返回前 k 个结果
    """
    # 1. Query 编码
    query_vector = embedder.encode(query)

    # 2. 向量检索
    results = vector_db.search(query_vector, top_k)

    return results
```

要求：
- 必须可读、可运行
- 关键步骤加注释
- 复杂逻辑加 docstring
- 错误处理要展示

#### 4. 表格

- 用于对比、汇总、清单
- 第一列为对比维度
- 单位、版本号必须标注

#### 5. 链接

- 站内链接用相对路径：`[2.1.1-编程语言深入浅出](./2.1.1-编程语言深入浅出.md)`
- 站外链接用完整 URL
- 关键引用用脚注

#### 6. ASCII 图

- 用于架构、流程、对比
- 优先用 ```text 代码块包裹
- 复杂流程考虑用 Mermaid

#### 7. Emoji

- 用于章节开头增强可读性
- 全文一致：✅ 🚧 📝 ⭐ 💡 ⚠️ ❌ 🎯 🔍 📚 💼
- 不要过度使用

---

## 🔖 提交规范

### Commit 消息格式

采用 [Conventional Commits](https://www.conventionalcommits.org/) 规范：

```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Type

- `docs`：文档变更
- `feat`：新增内容
- `fix`：修复错误
- `style`：格式调整（不影响内容）
- `refactor`：内容重构
- `chore`：杂项（构建、工具）

#### 示例

```bash
# 纠错
git commit -m "docs(2.1.2): 修正 ColBERT 章节一处笔误"

# 新增内容
git commit -m "feat(模块一): 新增医疗行业 FDE 实战案例"

# 重构
git commit -m "refactor(2.1): 统一所有子文件的章节结构"

# 多行（详细说明）
git commit -m "fix(2.1.5): 修正 Milvus 集群配置错误

- 修正副本数从 1 改为 3
- 添加 storageClassName 字段
- 移除已废弃的 imagePullPolicy

Closes #123"
```

### PR 规范

PR 标题与 commit 格式一致。

PR 描述必须包含：

```markdown
## 变更类型
- [ ] 纠错
- [ ] 新增章节
- [ ] 重构
- [ ] 其他（请说明）

## 变更内容
简述改了什么

## 关联 Issue
Closes #xxx / Related to #xxx

## 检查清单
- [ ] 内容准确无误
- [ ] 代码示例可运行
- [ ] 链接有效
- [ ] 格式符合规范
- [ ] 已本地预览
```

---

## 👀 审稿流程

1. **提交 PR** —— 创建 Pull Request
2. **自动检查** —— CI 自动跑格式检查、链接检查
3. **人工审稿** —— 维护者审阅内容准确性
4. **讨论修改** —— 可能有几轮讨论与修改
5. **合并** —— 审核通过后合并
6. **致谢** —— 贡献者列入 README

### 审稿标准

- ✅ 技术准确性
- ✅ 表达清晰度
- ✅ 是否符合读者地图
- ✅ 与已有内容的连贯性
- ✅ 中文表达规范

### 响应时间

- 初次响应：3 个工作日内
- 完成审稿：1-2 周内
- 复杂 PR：可能 1 个月+

---

## 🌟 贡献者

感谢所有为 FDE Handbook 做出贡献的人！

<!-- ALL-CONTRIBUTORS-LIST:START -->
<!-- 贡献者列表将自动更新 -->
<!-- ALL-CONTRIBUTORS-LIST:END -->

---

## 📮 联系方式

- **GitHub Issues**：提问题 / 建议
- **GitHub Discussions**：开放讨论
- **邮箱**：（待添加）

---

## ❓ 常见问题

**Q: 我没有 FDE 经验，能贡献吗？**
A: 可以！纠错、补充案例、提问都是贡献。

**Q: 内容来自哪里？**
A: 公开资料整理 + 行业调研。请勿提交未公开的客户数据。

**Q: 能直接翻译成英文吗？**
A: 当前 v1.1 以中文为主，英文版规划中。

**Q: 多久更新一次？**
A: 每季度回顾更新。

**Q: 能引用本仓库到我的文章 / 课程中吗？**
A: 可以，请保留原作者署名与链接。

---

**再次感谢你的贡献！** 🚀
