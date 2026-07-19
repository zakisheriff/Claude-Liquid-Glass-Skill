# <div align="center">Claude Liquid Glass Skill</div>

<div align="center">
<strong>A Claude Skill that enforces native iOS 26 Liquid Glass + mandatory haptics across SwiftUI, UIKit & React Native</strong>
</div>

<br />

<div align="center">

![Claude Skill](https://img.shields.io/badge/Claude-Skill-d97757?style=for-the-badge&logo=anthropic&logoColor=white)
![SwiftUI](https://img.shields.io/badge/SwiftUI-iOS%2026-0071e3?style=for-the-badge&logo=swift&logoColor=white)
![React Native](https://img.shields.io/badge/React%20Native-Expo-61dafb?style=for-the-badge&logo=react&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

<br />

<a href="https://github.com/zakisheriff/Claude-Liquid-Glass-Skill">
<img src="https://img.shields.io/badge/View%20on%20GitHub-Click%20Here-0071e3?style=for-the-badge&logo=github&logoColor=white" height="50" />
</a>

<br />
<br />

**[Get the Skill: github.com/zakisheriff/Claude-Liquid-Glass-Skill](https://github.com/zakisheriff/Claude-Liquid-Glass-Skill)**

</div>

<br />

> **"Never fake the glass. Never miss a haptic."**
>
> The Claude Liquid Glass Skill teaches Claude to build iOS UI the way Apple intended — using only
> native Liquid Glass components (iOS 26 / WWDC 2025), never hand-rolled glassmorphism, and firing a
> haptic on every single touch. It works for SwiftUI, UIKit, and React Native / Expo apps alike.

---

## 🌟 Vision

The Claude Liquid Glass Skill's mission is to be:

- **The default for every iOS UI Claude writes** — native Liquid Glass, never legacy flat/opaque styling
- **A single source of truth** across SwiftUI, UIKit, and React Native / Expo
- **A zero-compromise standard** — no custom-made glass, no silent taps, ever

---

## ✨ Why This Skill?

Left to defaults, AI assistants hand-roll "glassmorphism" with `.ultraThinMaterial`, blur stacks, and
opacity hacks — and forget haptics entirely. This skill hard-codes two laws into Claude: **(1) never
custom-make Liquid Glass — use the platform's own native primitive**, and **(2) every touch fires a
haptic.** The result is UI that looks and feels genuinely native on iOS 26.

---

## 🎨 Apple-Inspired "Liquid Glass" Design

- **Native material only**
  `.glassEffect()`, `.buttonStyle(.glass/.glassProminent)` in SwiftUI; `GlassView` / `GlassContainer` / `NativeTabs` in React Native.

- **Concentric & semantic**
  Shapes nest concentrically; tint is reserved for real state (destructive, primary, selection) — never decoration.

- **Grouped, morphing glass**
  Related controls blend as one shape via `GlassEffectContainer` / `GlassContainer`.

- **Accessibility-first**
  Degrades gracefully under Reduce Transparency, Increase Contrast, and Reduce Motion.

---

## 🤖 Cross-Platform Intelligence

- **SwiftUI / UIKit**
  Full component → API map, circular-icon idiom, tinted selectable glass, `.searchable`, sheets, toolbars.

- **React Native / Expo**
  `expo-glass-effect` + `expo-router` NativeTabs, availability gating, and platform-split layouts (`_layout.ios.tsx`).

- **Auto-triggering**
  Claude activates the skill on any iOS UI work — even "just make a button" — without being told "Liquid Glass."

---

## 🔐 Two Hard Laws

- **Never custom-make Liquid Glass**
  No `BlurView`/`.ultraThinMaterial`/opacity fakes on iOS. Custom `BlurView` docks allowed only as Android/Web fallback.

- **Every touch fires a haptic**
  Centralized `HapticManager` / `.hapticTap()` (SwiftUI) or `useHaptics()` over `expo-haptics` (RN). No silent taps.

---

## 🎓 What's Inside

- **`SKILL.md`**
  The full ruleset: two hard laws, golden rules, SwiftUI + RN component maps, snippets, and a review checklist.

- **Extended Reference**
  Concentricity, custom shapes, `glassEffectID` morphing, RN native-module details, haptic coverage, and iOS point-release quirks.

- **Battle-tested patterns**
  Distilled from real shipping apps (Halal-It in SwiftUI; Akhi-AI & Medhive in React Native / Expo).

---

## 📁 Project Structure

```
Claude-Liquid-Glass-Skill/
├── claude-liquid-glass/                        # The skill (drop this into .claude/skills/)
│   ├── SKILL.md                             # Core ruleset + frontmatter (name, description)
│   └── references/
│       └── liquid-glass-reference.md        # Extended reference & deep-dive snippets
├── claude-liquid-glass.zip                     # Same skill, zipped — for claude.ai upload
└── README.md
```

---

## 🚀 Quick Start

### Prerequisites

- **Claude Code** (CLI, desktop, or IDE extension) — or a **Claude.ai** account with Skills enabled
- An iOS project (SwiftUI / UIKit) or a React Native / Expo project

### 1. Clone the Repository

```bash
git clone https://github.com/zakisheriff/Claude-Liquid-Glass-Skill.git
cd Claude-Liquid-Glass-Skill
```

### 2. Install into Claude Code

```bash
# Personal — available in all your projects
cp -r claude-liquid-glass ~/.claude/skills/

# OR Project-scoped — shareable with your team via git
mkdir -p .claude/skills
cp -r claude-liquid-glass .claude/skills/
```

### 3. Install into Claude.ai / Desktop

- Open **Settings → Capabilities / Skills → Upload skill**
- Upload **`claude-liquid-glass.zip`**

### 4. Use It

The skill auto-triggers on any iOS UI work. Or invoke it explicitly:

```
/claude-liquid-glass
```

Now ask Claude to "add a nav bar" or "make a button" — it will produce native Liquid Glass with haptics. 🎉

---

## 🎯 Key Features

### For SwiftUI / UIKit
✅ **Native components** — `.glassEffect`, `.buttonStyle(.glass/.glassProminent)`, `.buttonBorderShape(.circle)`
✅ **Tinted selectable glass** — `.glassEffect(.regular.tint(color).interactive(), in:)`
✅ **Automatic chrome** — `NavigationStack`, `TabView`, `.searchable`, sheets adopt glass for free
✅ **Mandatory haptics** — `HapticManager` + `.hapticTap()` / `.sensoryFeedback`

### For React Native / Expo
✅ **Real native glass** — `expo-glass-effect` `GlassView` / `GlassContainer`
✅ **Native tab bar** — `expo-router` `NativeTabs` with SF Symbols
✅ **Availability gating** — `isLiquidGlassAvailable()` + Reduce Transparency → plain-`View` fallback
✅ **Mandatory haptics** — centralized `useHaptics()` over `expo-haptics`

---

## 🔧 Tech Stack

### The Skill
- **Markdown + YAML frontmatter** — `SKILL.md` (name, description, trigger rules)
- **Anthropic Agent Skills** format — folder-based, auto-discovered by Claude

### Targets It Governs
- **SwiftUI / UIKit** — iOS 26 Liquid Glass APIs
- **React Native / Expo** — `expo-glass-effect`, `expo-router/unstable-native-tabs`, `expo-haptics`, `expo-symbols`

---

## 🔒 Guardrails

✅ **No hand-rolled glass on iOS** — bans `.ultraThinMaterial` / `BlurView` / opacity fakes
✅ **No custom nav/tab/search bars** — must use native chrome
✅ **No silent taps** — every interactive element requires a haptic
✅ **No decorative tint** — tint must be semantic
✅ **Accessibility verified** — Reduce Transparency / Increase Contrast / Reduce Motion

---

## 📜 How Claude Uses It

- **Auto-trigger** — the `description` frontmatter makes Claude load the skill on any iOS UI task
- **Explicit** — invoke `/claude-liquid-glass` in Claude Code
- **Review mode** — the skill includes an audit checklist for refactoring existing code to native Liquid Glass

---

## 🌐 Distribution

### Claude Code
1. Copy `claude-liquid-glass/` into `~/.claude/skills/` (personal) or `.claude/skills/` (project)
2. Commit the project-scoped copy to share with your team

### Claude.ai / Desktop
1. Upload `claude-liquid-glass.zip` under Settings → Skills
2. Enable the skill for your workspace

---

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

---

## 📄 License

MIT License — 100% Free and Open Source

---

## ☕️ Support the Project

If the Claude Liquid Glass Skill saved you time or leveled up your iOS UI:

- Consider buying me a coffee
- It keeps development alive and motivates future updates

<div align="center">
<a href="https://buymeacoffee.com/theoneatom">
<img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="60" width="217">
</a>
</div>

---

<p align="center">
Made by <strong>Zaki Sheriff</strong>
</p>

<p align="center">
<em>Because great design should be free for everyone.</em>
</p>
