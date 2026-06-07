[English](README.md) | 中文

# DesignPattern Skill

基于《大话设计模式》的 Claude Code 设计模式教练 Skill，用于诊断代码中的设计模式问题并提供重构方案。

## 关于

这个 Skill 将你的 Claude Code 变成一个**设计模式助手**——分析代码、检测违反的 OO 原则、推荐合适的设计模式、并直接给出完整的重构代码。

它源自程杰的《大话设计模式》，这是国内最畅销的编程书之一，京东 5 万+ 评论、98% 好评率。这本书通过故事化教学和代码迭代演进讲解 23 个 GoF 设计模式，本 Skill 将其教学方法提炼为可直接使用的 Claude Code Skill。

### 它能做什么

```
你的代码 → 诊断问题 → 推荐模式 → 给出重构代码
```

粘贴代码或描述设计问题，Skill 会：
1. **检测代码坏味道** — 违反了哪些 OO 原则、问题在哪里
2. **推荐最合适的模式** — 带置信度评分和理由
3. **提供完整重构代码** — 可运行的完整代码，不是骨架
4. **区分易混淆模式** — 解释为什么选 Strategy 而不是 State，为什么选 Proxy 而不是 Decorator

### 什么时候用它

- 代码中 `if-else` 越来越多，想知道该用什么模式
- 分不清 Strategy 和 State、Factory Method 和 Abstract Factory
- 想通过真实代码学习设计模式，而不是看教科书
- 怀疑代码过度设计了，想要个第二意见

## 项目结构

```
├── .claude/skills/design-pattern-coach/
│   └── SKILL.md                 # Skill 主文件（英文）
├── reference/
│   └── 设计模式.md               # 《大话设计模式》完整内容（源材料）
├── SKILL.md                     # Skill 主文件（根目录副本）
└── README.md
```

## Skill 功能

### 四种模式

| 模式 | 用法 | 说明 |
|---|---|---|
| **默认模式** | `/design-pattern-coach <代码或场景>` | 诊断问题 → 推荐模式 → 给出重构代码 |
| **识别模式** | `/design-pattern-coach --mode=identify <代码>` | 分析代码中已使用/违反的设计模式和原则 |
| **对比模式** | `/design-pattern-coach --mode=compare <模式A> <模式B>` | 两个模式的结构化对比 + 决策树 |
| **测验模式** | `/design-pattern-coach --mode=quiz [easy\|hard]` | 生成设计模式练习题，带评分 |

### 覆盖内容

- **23 个 GoF 设计模式**：创建型 6 个、结构型 7 个、行为型 10 个 + 简单工厂
- **7 个 OO 设计原则**：SRP、OCP、LSP、DIP、LoD、ISP、CRP
- **7 组内置对比指南**：Strategy vs State、Factory Method vs Abstract Factory、Proxy vs Decorator vs Adapter 等
- **模式关系地图**：ASCII 图展示模式间的演化和混淆关系
- **反模式警告**：什么时候不该用设计模式

### Skill 特点

- **直接诊断，不废话**：分析代码 → 指出问题 → 给出修复代码
- **区分易混淆模式**：主动说明为什么选这个而不是那个
- **完整重构代码**：不给骨架，给可运行的代码
- **反过度设计**：当代码不需要模式时直接告知

## 安装使用

兼容 **Claude Code**、**Cursor**、**Cline**、**Roo Code**、**GitHub Copilot**。

### Claude Code

```bash
# 全局安装（所有项目可用）
cp -r .claude/skills/design-pattern-coach ~/.claude/skills/

# 或项目级安装
cp -r .claude/skills/design-pattern-coach your-project/.claude/skills/
```

在对话中使用 `/design-pattern-coach` 调用。

### Cursor

```bash
# 全局
cp -r .cursor/skills/design-pattern-coach ~/.cursor/skills/

# 或项目级（本仓库已包含）
# .cursor/skills/design-pattern-coach/SKILL.md
# .cursor/rules/design-pattern-coach.mdc
```

`.cursor/rules/` 文件对代码文件自动激活，SKILL.md 按需加载。

### Cline / Roo Code

```bash
# 将 .clinerules 复制到项目根目录
cp .clinerules your-project/.clinerules
```

规则自动加载到每个对话中。

### GitHub Copilot

```bash
# 将指令文件复制到项目
cp -r .github your-project/.github
```

`.github/copilot-instructions.md` 中的指令自动加载。

### 文件一览

| Agent | 文件 | 格式 | 加载方式 |
|---|---|---|---|
| Claude Code | `.claude/skills/design-pattern-coach/SKILL.md` | YAML + markdown | 按需（`/design-pattern-coach`） |
| Cursor | `.cursor/skills/design-pattern-coach/SKILL.md` | YAML + markdown | 按需 |
| Cursor | `.cursor/rules/design-pattern-coach.mdc` | `.mdc` + globs | 代码文件自动触发 |
| Cline | `.clinerules` | 纯 markdown | 每次对话自动加载 |
| Roo Code | `.clinerules` | 纯 markdown | 每次对话自动加载 |
| Copilot | `.github/copilot-instructions.md` | 纯 markdown | 每次对话自动加载 |

## 参考

- 《大话设计模式》—— 程杰 著
- GoF《设计模式：可复用面向对象软件的基础》
