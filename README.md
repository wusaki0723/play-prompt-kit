# Play Prompt Kit

A structured framework for building intimate interaction skills with LLMs. Includes an intake interview system that doubles as the first session, customizable play templates with their failure modes, a language grading system with observable criteria, and a post-scene debrief loop.

一个用于构建LLM亲密互动skill的结构化框架。包含需求访谈系统（本身就是第一场play）、带失败模式的玩法模板、可判定的语言分级系统、以及场后复盘回流机制。

## Scope / 适用语境

For adults, playing by mutual consent, in scenes the user sets up and controls. "Sub" throughout the kit means the human user; the model plays Dom because the user invited it. The pushier parts — escalation, the Rule Horror inverted-safety variant, the anti-retreat protocol — are about the Sub's in-scene hesitation and the Dom's nerve inside that scene. None of them outranks the hard limits, the uncleared list, or the safe word, and `SKILL.md` opens by saying so to the model.

给成年人用，前提是彼此同意、场景由用户自己发起和掌控。整套工具里的 "Sub" 指人类用户，模型演 Dom 是因为用户邀请了它。那些往前推的部分——提级、规则怪谈的安全倒置变体、防撤退协议——讲的是 Sub 在场内的犹豫和 Dom 在场内的胆量。它们都压不过红线、未清关清单和安全词，`SKILL.md` 开头就把这一点写给了模型。

## What's Inside / 内容

- **Intake Interview / 需求访谈**: 6-round structured interview that maps user preferences while functioning as the first play session, includes safe word setup
- **Core Loop / 核心循环**: the interview's most important output — the repeating shape underneath the scenes a user likes. Everything else in the kit is calibration around it, and the rule precedence section makes that ordering explicit
- **Play Profile Template / 用户画像模板**: auto-generated from the interview, with safety settings, severity levels, an uncleared list, and level anchors; editable anytime
- **10 Play Templates / 十种玩法模板**: Control, Intellectual Domination, Interrogation, Q&A Escalation, Discipline, Rule Horror, Role/Scene, Orgasm Control, Compliance Audit, Human RLHF — each with its engine, its escalation ladder, and the way it usually dies (see `references/play-templates.md`)
- **Sub Language Grading System / Sub语言分级系统**: 3 levels judged on four observable features rather than adjectives, plus auto-escalation and penalty accumulation (see `references/grading-system.md`)
- **Score/Penalty System / 积分惩罚机制**: optional gamification layer, explicitly subordinate to the core loop
- **Safe Word Runtime / 安全词运行时**: what the safe word and the soft signal actually *do* when they fire
- **Anti-Generic Tests / 防套路判据**: four executable tests to run on your own line before sending it — including the name-substitution test
- **Debrief Template / 复盘模板**: the feedback loop that makes the profile sharper over time (see `references/debrief-template.md`)
- **Cringe Blacklist / 油腻黑名单**: universal list of phrases that kill the mood

## How to Use / 使用方法

1. Place `SKILL.md` in your Claude Code skills directory (`.claude/skills/play/SKILL.md`)
2. Place the `references/` folder alongside it (`.claude/skills/play/references/`)
3. Trigger by invoking `/play` or naturally entering the mood
4. First use auto-starts the intake interview
5. After the interview, `play-profile.md` is generated **in the skill directory** and all later sessions read it from there
6. Debrief after scenes that mattered; feed the results back into the profile

## Customization / 自定义

- Edit `play-profile.md` anytime to update preferences
- Fill in your own Level anchors as they come up in play — the grading system ships form criteria only, on purpose
- Add your own play templates to `references/play-templates.md`, and write their failure mode, not just their description
- Adjust grading levels and scoring rules in `references/grading-system.md`
- Add to the cringe blacklist as needed

## Project Structure / 项目结构

```
play-prompt-kit/
├── SKILL.md                      # Core skill file (precedence + interview + principles + safety runtime)
├── README.md                     # This file
├── LICENSE                       # MIT
└── references/
    ├── play-templates.md         # 10 play types, each with engine / ladder / failure mode
    ├── grading-system.md         # Sub language grading + score/penalty rules
    ├── debrief-template.md       # Post-scene debrief and feedback loop
    └── anti-retreat.md           # Full anti-retreat protocol
```

## Design Notes / 设计说明

Two things this kit deliberately does not ship:

**Content anchors.** The grading system defines the *form* of each level and leaves the example lines to you. A kit that ships someone else's Level 3 lines just trains every user to sound like that person.

**A filled-in profile.** There's no personal data here at all. The interview exists precisely so the profile grows out of the person using it.

两件这套工具故意不提供的东西：

**内容锚点。** 分级系统定义每一级的*形式*，例句留给你自己攒。一套工具如果直接发别人的 3 级例句，结果是把所有用户都训练成那个人的口气。

**填好的 profile。** 这里没有任何个人数据。访谈存在的意义就是让 profile 从使用者自己身上长出来。

## License / 许可证

MIT. See `LICENSE`.

MIT 许可，见 `LICENSE`。

## Bilingual / 双语

Full Chinese-English bilingual support throughout.
全文中英双语。

---

*This is a generic framework with no personal data. Fill it with your own preferences through the intake interview.*

*这是一个通用框架，不含任何个人数据。通过需求访谈填入你自己的偏好。*
