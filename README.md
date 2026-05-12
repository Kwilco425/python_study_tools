# Python Study Toolkit

A set of self-contained, interactive web quizzes I built while learning Python — designed to make active recall less painful and more engaging than flipping flashcards.

Each quiz is a single HTML file. No build step, no server, no dependencies. Open the file in any browser and start studying.

![Status](https://img.shields.io/badge/status-active-brightgreen) ![Built with](https://img.shields.io/badge/built%20with-HTML%20%2F%20CSS%20%2F%20vanilla%20JS-blue) ![License](https://img.shields.io/badge/license-MIT-purple)

---

## Why this exists

I'm a sole proprietor going back to school for programming, and I noticed that paper flashcards and standard Quizlet drills weren't sticking. The questions felt context-free, the wrong answers didn't teach me anything, and I'd finish a deck without knowing which topics were actually weak.

So I built these. Each quiz:

- Tracks score in real time
- Shows the correct answer when I get one wrong, with a plain-English explanation
- Gives me a **memory trick** for every question so the concept has a hook to hang on
- Provides a halfway check-in at question 15
- Generates a **final report** at the end with strengths, focus areas, and targeted study tips broken down by topic — not just a percentage

It's the study tool I wished I had.

---

## The quizzes

| File | Topics |
|------|--------|
| `quizzes/01-python-foundations.html` | Multiple-choice review of Python basics — types, loops, slicing, conditionals, plus typed-in code questions with a real code editor that grades against test cases |
| `quizzes/02-python-syntax-round1.html` | Variables, scope, data types, type conversion, strings, slicing, booleans, operators, dictionaries |
| `quizzes/03-python-syntax-round2.html` | String methods deep dive (`.strip`, `.split`, `.join`, `.replace`), f-strings, `.format()`, number formatting, alignment, membership |
| `quizzes/04-python-paradigms-and-builtins.html` | Programming paradigms (imperative, OOP, functional, declarative), built-in functions (`len`, `type`, `sum`, `range`, `sorted`, `any`/`all`, `dir`, `help`), variables, scope |
| `quizzes/05-data-structures.html` | Lists, tuples, sets, dictionaries — definitions, when to use each, and the full method suite for each (`append` vs `extend`, `remove` vs `discard`, `pop`, `update`, `clear`) |

Each quiz is 30 questions and takes about 15–25 minutes.

---

## How to use them

### Option 1: Just open the file

Clone or download, then double-click any `.html` file in the `quizzes/` folder. Works in any modern browser, fully offline.

```bash
git clone https://github.com/Kwilco425/python-study-toolkit.git
cd python-study-toolkit
open quizzes/01-python-foundations.html      # macOS
xdg-open quizzes/01-python-foundations.html  # Linux
start quizzes/01-python-foundations.html     # Windows
```

### Option 2: Host on GitHub Pages

Push to GitHub, enable Pages in Settings, and your quizzes become playable from any URL like:

```
https://Kwilco425.github.io/python-study-toolkit/quizzes/01-python-foundations.html
```

No setup beyond flipping the Pages toggle in your repo settings.

---

## Design notes

A few decisions worth calling out for anyone curious about how these are built:

### Code questions actually execute

The foundations quiz lets you type Python directly into an in-browser code editor for function-writing questions. To avoid pulling in a heavy Python-in-the-browser runtime, I wrote a small Python-to-JavaScript translator that handles the subset of Python the questions use (`def`, `return`, `if/else`, `for x in y`, `len()`, negative indexing, `.append()`, `.isalpha()`, `.isdigit()`, default parameter values, etc.). It's pragmatic, not complete — but it means the code is graded against real test cases, not just string matching.

### Mistakes are first-class

Most quizzes treat a wrong answer as a dead end. These show you the correct answer in green, your wrong answer in red, and then write a sentence or two about *why* the correct answer is correct. The memory trick gets attached to every question regardless of whether you got it right, because the goal is retention, not just scoring.

### Topic-level feedback

Each question is tagged by topic. At the end, the final card pulls the wrong answers into a "focus areas" section and the strong topics into a "strengths" section, then generates a **targeted study guide** based on which topics actually tripped you up — not generic advice.

### Visual design

Dark theme with monospace typography across the board. Each quiz has a slightly different accent color (purple, teal, amber, green) so you can tell them apart at a glance. CSS-only — no frameworks, no Tailwind, no build step. The entire styling is in a single `<style>` block at the top of each file.

### Self-contained

Every quiz is one HTML file. No external JavaScript libraries, no fonts loaded from CDNs, no API calls. You could put one on a USB drive and run it on a computer with no internet. This matters for studying somewhere with bad Wi-Fi.

---

## Tech stack

- HTML5
- CSS3 (CSS custom properties for theming, no preprocessors)
- Vanilla JavaScript (no framework, no build step)
- ~600 lines per quiz, all in one file

---

## A note on the questions

The question content was written specifically for these quizzes as I worked through study material. I rewrote everything in my own words and added the explanations and memory tricks myself. They cover **general Python concepts** that show up in most introductory courses — not any one specific course's content.

If you spot a factual error in a question, please open an issue! I'd rather fix it than have someone else learn the wrong thing.

---

## What's next

- [ ] Round 5 (functions deep dive, control flow, error handling, file I/O, modules)
- [ ] Spaced-repetition mode that re-asks missed questions a day later
- [ ] Optional dark/light theme toggle
- [ ] Question bank shuffling so retakes feel different
- [ ] Export your results as Markdown to drop into a study journal

---

## License

[MIT](LICENSE) — use it, fork it, remix it, build your own version. If you make something cool with it, I'd love to see it.
