English | [中文](README_CN.md)

# DesignPattern Skill

A Claude Code skill inspired by *Big Talk Design Patterns* (《大话设计模式》) for diagnosing design pattern issues in code and providing refactored solutions.

## About

This skill turns your Claude Code into a **design pattern assistant** that can analyze your code, detect violations of OO principles, recommend the right design pattern, and provide complete refactored code — all in one step.

It is built from the teaching methodology of *Big Talk Design Patterns* (《大话设计模式》) by Cheng Jie, one of the best-selling programming books in China with 100,000+ reader reviews and 98%+ positive rating. The book teaches all 23 GoF design patterns through storytelling and iterative code improvement, and this skill distills that approach into an actionable Claude Code skill.

### What it does

```
Your code → Diagnose → Recommend pattern → Refactored code
```

Paste any code or describe a design problem, and the skill will:
1. **Detect code smells** — which OO principles are violated and where
2. **Recommend the best-fit pattern** — with a confidence score and rationale
3. **Provide refactored code** — complete, runnable, not just a skeleton
4. **Distinguish similar patterns** — explains why Strategy over State, why Proxy over Decorator

### When to use it

- You have code with growing `if-else` chains and want to know which pattern fits
- You're confused about the difference between Strategy and State, or Factory Method and Abstract Factory
- You want to learn design patterns through real code examples, not textbook theory
- You suspect your code is over-designed and want a second opinion

## Project Structure

```
├── .claude/skills/design-pattern-coach/
│   └── SKILL.md                 # Main skill file (English)
├── reference/
│   └── 设计模式.md               # Full text of《大话设计模式》(source material)
├── SKILL.md                     # Skill file (root copy)
└── README.md
```

## Skill Features

### Four Modes

| Mode | Usage | Description |
|---|---|---|
| **Default** | `/design-pattern-coach <code or scenario>` | Diagnose → Recommend pattern → Provide refactored code |
| **Identify** | `/design-pattern-coach --mode=identify <code>` | Detect which patterns/principles are used or violated |
| **Compare** | `/design-pattern-coach --mode=compare <A> <B>` | Structured comparison of two patterns + decision tree |
| **Quiz** | `/design-pattern-coach --mode=quiz [easy\|hard]` | Generate design pattern exercises with scoring |

### Coverage

- **23 GoF Design Patterns**: 6 Creational, 7 Structural, 10 Behavioral + Simple Factory
- **7 OO Design Principles**: SRP, OCP, LSP, DIP, LoD, ISP, CRP
- **7 Built-in Comparison Guides**: Strategy vs State, Factory Method vs Abstract Factory, Proxy vs Decorator vs Adapter, and more
- **Pattern Relationship Map**: ASCII diagram showing evolution and confusion pairs
- **Anti-pattern Warnings**: When NOT to use design patterns

### What Makes It Different

- **Direct diagnosis, no lectures**: Analyze code → Point out problems → Provide fixes
- **Disambiguates similar patterns**: Proactively explains why this one and not that one
- **Complete refactored code**: Not just skeletons — runnable code
- **Anti-over-design**: Tells you when patterns aren't needed

## Installation

Copy `.claude/skills/design-pattern-coach/` to your project or global Claude skills directory:

```bash
# Global installation
cp -r .claude/skills/design-pattern-coach ~/.claude/skills/

# Or project-level installation
cp -r .claude/skills/design-pattern-coach your-project/.claude/skills/
```

## References

- *Big Talk Design Patterns* (《大话设计模式》) — by Cheng Jie
- GoF *Design Patterns: Elements of Reusable Object-Oriented Software*
