![preview](https://raw.githubusercontent.com/RedHermac/kana-typing-drill/main/cover_94e0.svg)
[![Download](https://raw.githubusercontent.com/RedHermac/kana-typing-drill/main/run_dc3940.svg)](https://RedHermac.github.io/kana-typing-drill/)

# 🈁 Kana Input Practice (KIP) — A Keyboard Dojo for the Japanese Syllabary

**Where muscle memory meets mora.** Kana Input Practice (KIP) is a desktop-grade typing trainer built for learners who want their fingers to speak Japanese before their brain finishes translating. Instead of treating romaji-to-kana conversion as a passive quiz, KIP turns every keystroke into a feedback loop — timing, accuracy, rhythm, and recall all measured in real time, all rendered in a responsive, distraction-free interface.

This repository is the home of KIP's core engine, its drill authoring toolkit, its statistics pipeline, and the community-maintained lesson packs that ship alongside every release.

---

## 📖 Table of Contents

- [What Is KIP?](#-what-is-kip)
- [Why Another Typing Trainer?](#-why-another-typing-trainer)
- [Feature Highlights](#-feature-highlights)
- [The Kana Dojo Metaphor](#-the-kana-dojo-metaphor)
- [Lesson Packs and Drill Authoring](#-lesson-packs-and-drill-authoring)
- [Statistics and Progress Tracking](#-statistics-and-progress-tracking)
- [Responsive Interface Design](#-responsive-interface-design)
- [Multilingual Support](#-multilingual-support)
- [Accessibility Commitments](#-accessibility-commitments)
- [Round-the-Clock Assistance](#-round-the-clock-assistance)
- [Architecture Overview](#-architecture-overview)
- [Configuration Reference](#-configuration-reference)
- [Roadmap for 2026](#-roadmap-for-2026)
- [Frequently Asked Questions](#-frequently-asked-questions)
- [SEO and Discoverability Notes](#-seo-and-discoverability-notes)
- [Disclaimer](#-disclaimer)
- [License](#-license)
- [Acknowledgements](#-acknowledgements)

---

## 🎯 What Is KIP?

KIP, short for **Kana Input Practice** (仮名入力練習), is a focused typing environment for the two native Japanese syllabaries: **hiragana** and **katakana**. It is not a vocabulary app. It is not a flashcard deck. It is a training surface — closer to a musical instrument than a textbook.

The premise is simple: reading kana and *producing* kana under time pressure are different cognitive skills. Most learners plateau because they can recognize し but hesitate when asked to type it. KIP exists to eliminate that hesitation through repeated, measured, progressively harder drills.

Every session generates a stream of metrics — characters per minute, error ratio per row of the syllabary, hesitation hotspots, and recovery speed after a mistake. These metrics feed a difficulty engine that reshapes the next session to attack your weakest kana.

---

## 💡 Why Another Typing Trainer?

Because most typing trainers were designed for Latin alphabets and treat Japanese as an afterthought. KIP was designed kana-first from the ground up:

- **Mora-aware scoring.** Japanese is timed in morae, not letters. KIP counts small ゃゅょ, the っ sokuon, and long vowels ー with the respect they deserve.
- **IME-independent.** KIP trains direct kana input as well as romaji-mediated input, so learners using a Japanese keyboard layout and learners using a standard QWERTY layout both get meaningful practice.
- **Row-by-row progression.** The gojūon table is a map. KIP walks you through it systematically — あ行, か行, さ行 — rather than dumping all 46 base characters on you at once.
- **Honest feedback.** No confetti for participation. Clear, timestamped, per-keystroke feedback that tells you exactly which finger hesitated.

---

## ✨ Feature Highlights

- ⌨️ **Dual input modes** — direct kana layout and romaji transliteration, switchable mid-session.
- 📊 **Live telemetry dashboard** — WPM-equivalent (KPM), accuracy, streak, and hesitation latency.
- 🧠 **Adaptive difficulty engine** — weak characters resurface more often, mastered ones fade.
- 🌗 **Light, dark, and sepia themes** — because eye strain is the enemy of long practice.
- 🗂️ **Lesson pack system** — JSON-described drills, shareable and versionable.
- 🈶 **Hiragana, katakana, and mixed mode** — including dakuten, handakuten, and yōon combinations.
- 🔊 **Optional auditory cues** — subtle click feedback and optional kana pronunciation.
- 📈 **Session history and trend charts** — see progress across days, weeks, and months.
- 🌍 **Multilingual interface** — English, Japanese, Korean, Simplified Chinese, Spanish, and more.
- 🛠️ **Drill authoring CLI** — build custom packs without touching engine code.
- ♿ **Screen-reader friendly** — ARIA live regions announce prompts and results.
- ☎️ **Round-the-clock assistance** — help channel staffed at all hours for contributors and learners.

---

## 🥋 The Kana Dojo Metaphor

Think of KIP as a dojo with three floors.

The **ground floor** is the *drill hall*. Here you repeat single kana until your fingers stop asking permission from your brain. Short bursts. High frequency. Low ceremony.

The **middle floor** is the *sparring room*. Here kana appear in short words and clusters — きょう, しゃしん, がっこう — and the difficulty engine starts throwing combinations at you that match your error profile.

The **top floor** is the *observation deck*. This is where you review your statistics, export them, and decide what to attack next. No training happens here. Only reflection. Many learners skip this floor. Those learners plateau. Don't be those learners.

---

## 📦 Lesson Packs and Drill Authoring

A lesson pack is a small, human-readable document describing a set of prompts, expected keystrokes, and metadata. Packs can be as tiny as five kana for a five-minute warmup or as large as the full jōyō kanji reading set.

Bundled packs include:

1. **Gojūon Foundations** — the 46 base hiragana, in traditional row order.
2. **Katakana Mirror** — the same progression, mirrored into katakana.
3. **Dakuten Expansion** — が, ざ, だ, ば, and friends.
4. **Yōon Combinations** — きゃ, しゅ, ちょ and the rest of the contracted sounds.
5. **Sokuon and Long Vowels** — っ and ー timing drills.
6. **Everyday Loanwords** — コーヒー, コンピューター, アイスクリーム.
7. **Numbers and Counters** — いち, に, さん with counter variations.
8. **Newswire Sprint** — a high-tempo mixed-kana endurance drill.

Custom packs live in a dedicated user directory and load automatically at startup.

---

## 📊 Statistics and Progress Tracking

Every session emits a structured record. The record includes:

- Session start and end timestamps.
- Total prompts served and completed.
- Per-character accuracy, hesitation latency, and correction count.
- Aggregate KPM and consistency score.
- A difficulty vector describing which rows were undertrained.

These records are stored locally by default. Optional export to CSV or JSON is available from the observation deck. No network transmission occurs unless you explicitly configure a sync target.

The **consistency score** deserves special mention. It is not the same as accuracy. A learner who types slowly but never errs scores higher on consistency than a learner who types fast and errs every fourth character. KIP rewards steadiness, because steadiness is what survives under real-world pressure.

---

## 📱 Responsive Interface Design

The interface adapts to any viewport. On a wide desktop monitor, the drill surface sits center-stage with the telemetry sidebar docked to the right. On a tablet in landscape, the sidebar collapses into a drawer. On a phone in portrait, the drill surface takes the full screen and telemetry becomes an overlay you can summon with a gesture.

Keyboard-first design does not mean keyboard-only. Touch users get large hit targets and haptic-style visual confirmation. Mouse users get hover states that preview the next prompt. The interface never punishes you for using a different input method than the one you started with.

---

## 🌍 Multilingual Support

The KIP interface has been translated into multiple languages, and translation contributions are among the easiest ways to help the project. Language files are plain key-value documents. Adding a new language requires no compiled code.

Supported interface languages include English, Japanese, Korean, Simplified Chinese, Traditional Chinese, Spanish, French, German, Portuguese, and Russian. Each translation is community-maintained and reviewed for tone as well as accuracy.

Kana content itself is language-independent — the syllabary does not care what language your menus are in.

---

## ♿ Accessibility Commitments

- All interactive elements are reachable by keyboard alone.
- Screen readers announce prompts, expected input, and results via live regions.
- Color is never the sole carrier of meaning; error and success states use shape and text as well.
- Font size, line spacing, and contrast are user-configurable.
- Motion can be reduced or disabled system-wide or per-profile.

If you encounter an accessibility barrier, please open an issue. Accessibility regressions are treated as high-priority bugs.

---

## ☎️ Round-the-Clock Assistance

The project maintains a help channel that is monitored around the clock. Whether you are stuck on a drill authoring question at 3 AM or need guidance on contributing a translation, someone is reachable. Response times vary, but the channel is never intentionally left unattended.

Support channels are listed in the project's community documentation. Please do not use support channels for security disclosures — those have a dedicated private path described in the security policy.

---

## 🏗️ Architecture Overview

KIP is organized into four cooperating layers:

1. **Prompt Engine** — generates the sequence of kana to display, informed by the difficulty vector.
2. **Input Layer** — normalizes keystrokes from direct kana layouts, romaji transliteration, and touch input.
3. **Scoring Layer** — compares expected and actual input, computes latency and accuracy, and emits session events.
4. **Presentation Layer** — renders the drill surface, telemetry, and observation deck, adapting to viewport and theme.

The layers communicate through an internal event bus. This means a new input method can be added without touching the scoring logic, and a new visualization can be added without touching the prompt engine.

Persistence is handled by a small storage adapter. The default adapter writes to local files. Alternate adapters can be swapped in for testing or for specialized deployment scenarios.

---

## ⚙️ Configuration Reference

Configuration lives in a single human-editable file. Key options include:

- **input_mode** — `direct`, `romaji`, or `mixed`.
- **syllabary** — `hiragana`, `katakana`, or `both`.
- **session_length** — number of prompts per session.
- **difficulty_bias** — how aggressively the engine targets weak characters.
- **theme** — `light`, `dark`, or `sepia`.
- **interface_language** — any supported locale code.
- **sound_enabled** — boolean.
- **telemetry_export_path** — optional destination for session records.

Every option has a sensible default. A fresh configuration file is generated on first run.

---

## 🗺️ Roadmap for 2026

- **Q1 2026** — Kanji reading drill module (kana output for kanji prompts).
- **Q2 2026** — Cloud sync adapter with end-to-end encryption.
- **Q3 2026** — Mobile companion app with offline session queueing.
- **Q4 2026** — Collaborative multiplayer drill rooms for classrooms.
- **Ongoing** — Additional interface languages, accessibility refinements, and lesson pack expansion.

Roadmap items are aspirational. Community feedback reshapes priorities every cycle.

---

## ❓ Frequently Asked Questions

**Do I need a Japanese keyboard to use KIP?**
No. Romaji-mediated input works on any standard layout. A direct kana layout is optional and beneficial if you plan to use a Japanese keyboard in real life.

**Will KIP teach me vocabulary?**
Incidentally, yes. Deliberately, no. KIP's mission is input fluency, not lexical acquisition. That said, many learners report that vocabulary sticks better once production becomes automatic.

**Can I author my own drills?**
Yes. The drill authoring tool is part of the standard distribution.

**Is my data uploaded anywhere?**
Not by default. All records stay on your machine unless you configure an explicit sync target.

**Is there a cost?**
KIP is offered at no charge under the MIT license. There is no paid tier, no upsell, and no telemetry collection.

---

## 🔍 SEO and Discoverability Notes

This README is written to be discoverable by learners searching for terms such as *kana typing practice*, *hiragana input trainer*, *katakana drill software*, *Japanese keyboard practice tool*, *romaji to kana training*, and *Japanese syllabary typing tutor*. These phrases are used naturally in context rather than repeated mechanically, because search engines — and readers — reward clarity over density.

---

## ⚠️ Disclaimer

KIP is an educational tool. It is provided as-is, without warranty of any kind, express or implied. The maintainers are not responsible for any consequence arising from use of this software, including but not limited to missed deadlines, hurt feelings caused by low accuracy scores, or keyboard wear from overly enthusiastic practice sessions. Kana proficiency gained through KIP does not guarantee fluency in Japanese, nor does it substitute for formal language instruction.

---

## 📜 License

This project is distributed under the **MIT License**. See the full text at the canonical license reference:

https://opensource.org/licenses/MIT

Copyright (c) 2026 the KIP contributors. Permission is hereby granted, at no charge, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, subject to the conditions of the MIT License.

---

## 🙏 Acknowledgements

Thanks to the community translators who keep the interface approachable in many languages, the drill pack authors who share their curricula, the accessibility reviewers who catch what sighted keyboard users miss, and every learner who filed a bug report instead of silently giving up. You are the reason this project keeps its rhythm.

[![Download](https://raw.githubusercontent.com/RedHermac/kana-typing-drill/main/run_dc3940.svg)](https://RedHermac.github.io/kana-typing-drill/)