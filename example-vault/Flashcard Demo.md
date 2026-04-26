---
title: Flash Card Demo
author: JT
date: 2026-04-15
tags: demo, flashcards, study
---
## How to Use Flash Cards

1. Click the **play button** in the editor toolbar and select **Flash Cards**
2. Press **Space** or **click** anywhere to reveal the answer
3. Rate your recall: **Again** (1) · **Hard** (2) · **Good** (3) · **Easy** (4)
4. Cards you struggle with come back sooner — spaced repetition learns what you know

### Formatting Your Cards

Separate cards with `---` and split question from answer with `???`:

```
What is the capital of France?

???

Paris

---

Next question here

???

Next answer here
```

- Cards without `???` show as question-only (no reveal)
- You can use **any Markdown** in questions and answers — code blocks, math, images, tables
- The **shuffle** button randomizes order while keeping Q&A paired
- Your progress is saved automatically and persists between sessions

### Tip: Use AI to Generate Cards

Paste your study material and ask the AI to format it:

> "Turn these notes into flash cards using --- and ??? syntax"

The AI system prompt knows the format. You can also attach a file for context.

---

What is the capital of France?

???

Paris

---

Explain recursion

???

A function that calls itself. Every recursive function needs:
- A **base case** that stops the recursion
- A **recursive case** that calls itself with a smaller problem

---

What is the largest planet in our solar system?

???

Jupiter

---

What does HTML stand for?

???

HyperText Markup Language

---

Who wrote "Romeo and Juliet"?

???

William Shakespeare

---

What is the speed of light in a vacuum?

???

Approximately **299,792,458 m/s** (or ~300,000 km/s)

---

What is the chemical symbol for gold?

???

**Au** (from Latin *aurum*)

---

How many continents are there?

???

Seven: Africa, Antarctica, Asia, Australia, Europe, North America, South America

---

What is the Pythagorean theorem?

???

$a^2 + b^2 = c^2$

Where $c$ is the hypotenuse of a right triangle.

---

Who painted the Mona Lisa?

???

Leonardo da Vinci (c. 1503–1519)

---

What is the smallest prime number?

???

**2** — it's also the only even prime number.

---

What does CPU stand for?

???

Central Processing Unit
