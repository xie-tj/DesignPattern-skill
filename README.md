[English](README_EN.md) | 中文

# DesignPattern Skill

基于《大话设计模式》的 Claude Code 设计模式教练 Skill，用于诊断代码中的设计模式问题并提供重构方案。

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

将 `.claude/skills/design-pattern-coach/` 目录复制到你的项目或全局 Claude skills 目录：

```bash
# 全局安装
cp -r .claude/skills/design-pattern-coach ~/.claude/skills/

# 或项目级安装
cp -r .claude/skills/design-pattern-coach your-project/.claude/skills/
```

## 参考

- 《大话设计模式》—— 程杰 著
- GoF《设计模式：可复用面向对象软件的基础》
