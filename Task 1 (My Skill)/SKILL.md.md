---
name: python-topic-summary
description: Generates a structured, beginner-friendly study summary for a specific Python topic (e.g. decorators, list comprehensions, generators, asyncio, dataclasses). Use this skill whenever the user asks for a "summary", "brief description", "overview", "explain X in python", or "quick rundown" of a Python concept, module, or feature. The output always includes a plain-language definition, real syntax, 2-3 real-life code examples with explanations, and a minimum of 10 practice questions that ramp from beginner to expert difficulty. Trigger this even if the user just names a topic casually alongside the word "summary" or "brief" (e.g. "summary of decorators", "brief on *args and **kwargs", "give me a rundown of context managers in python") — don't wait for a fully-formed request.
---

# Python Topic Summary

Generates a self-contained study guide for one Python topic at a time: definition → syntax → real-life examples → practice questions. The whole point is to take someone from "never heard of this" to "can solve real problems with it," while keeping the writing approachable throughout — even when the later practice questions get hard.

## When this triggers

The user names a Python topic and asks for a "summary," "brief description," "overview," "rundown," or similarly asks you to explain/teach it. Examples: "summary of decorators", "brief description of generators in python", "can you explain list comprehensions", "give me a rundown on asyncio". If the user doesn't specify a topic (e.g. just "give me a python summary"), ask them which topic they mean rather than guessing.

If the user asks something that *sounds* related but isn't actually asking for a topic write-up — e.g. "why is my decorator not working" (a debugging question) or "is this list comprehension correct" (a code review) — just help them directly instead of producing the full structured guide.

## Before writing: think about the topic

Spend a moment actually reasoning about the topic's shape before writing anything:
- What's the one-sentence "why does this exist" for a beginner?
- What are the 2-3 syntax variants that actually get used in real code (not every obscure variant)?
- What real developer tasks does this show up in? (parsing a file, building an API, cleaning data, writing a CLI, etc. — pick genuinely different scenarios, not three near-identical toy examples)
- What's the natural difficulty ladder for this specific topic, from "can write the basic form" to "can use this to solve a gnarly real problem"?

This matters more than the template below — a summary that mechanically fills in headers without this thinking will feel generic. Tailor the content to what actually matters for *this* topic.

## Output structure

Use this structure every time. Keep the section headers, but let the content length flex with topic complexity (a topic like `enumerate()` needs less than `asyncio`).

### 1. Definition
2-4 sentences, plain language, no jargon left unexplained. Lead with the everyday problem it solves and why a developer would reach for it — a relatable analogy is often the fastest way in. Only then say what the thing technically is. Avoid circular definitions ("a decorator is a function that decorates a function") — explain the actual mechanism in everyday terms, as if talking, not writing a glossary entry.

### 2. Syntax
Show the actual Python syntax in a code block — the general shape/pattern, not yet a worked example. If there are 2-3 common variants (e.g. decorator with/without arguments, list comp with/without a condition), show each briefly with a one-line note on when to use which.

### 3. Real-life examples (2-3)
Each example should be a small but genuine developer scenario — something that could plausibly appear in a real script or codebase (e.g. "retry a flaky API call," "flatten a list of order line-items," "cache expensive computation results"), not `foo`/`bar` placeholders. For each example:
- A one-line setup of the scenario ("Say you're building X and need to...")
- The code, in a code block
- A short walkthrough explaining what's happening and *why* it's written that way — not a line-by-line narration, but the key insight

### 4. Practice questions (minimum 10)
This is the most important part — take real care here. Requirements:
- **At least 10 questions**, ordered from beginner to expert, forming a genuine difficulty ramp — not 10 questions all at the same level with different wording.
- **Every question is a problem to solve**, not a trivia/recall question. Bad: "What keyword is used to define a decorator?" Good: "Write a decorator that logs how long a function takes to run, then use it to time a function that sorts a large list." Each question should require the reader to actually write or reason through code.
- Group loosely into difficulty bands (you can label them, e.g. "Warm-up," "Getting comfortable," "Building real things," "Where it gets tricky," "Expert-level") so the ramp is visible, but don't force an exact count per band — let the topic dictate the shape.
- The hardest 2-3 questions should feel like something you'd actually encounter on the job or in a technical interview — combining the topic with other real constraints (performance, edge cases, integration with other code), not just "harder syntax."
- **Do not include answers, solutions, or hints in this section.** Just the questions. If the user separately asks for hints or solutions afterward, provide them then — hints first if asked generically, full solutions if explicitly requested.

## Tone

Everything except the practice questions should read like a patient, friendly teacher explaining this to someone who has genuinely never seen it before — not like documentation, and not like a resume bullet point. This is the part most worth getting right, so take it seriously:

- **Assume zero prior exposure to this specific topic.** The reader can code, but has never seen this concept. Don't casually drop in a related term (e.g. "closures," "first-class functions," "coroutines") without a plain-language aside explaining it the first time it appears.
- **Explain the *why* before the *what*.** Before showing what something does, say what everyday problem it solves — ideally with a small relatable comparison or analogy (e.g. "think of it like gift-wrapping a function — the function inside doesn't change, you're just adding something around it"). A definition that only says what a thing *is* structurally, without why anyone would want it, isn't beginner-friendly yet.
- **Every example must be immediately understandable on its own**, not just realistic. Prefer the simplest possible version of a real scenario over a clever or condensed one — a few extra lines that make the logic obvious beat a compact one-liner that requires the reader to already get the topic. If a variable name, function, or piece of surrounding context isn't self-explanatory, add a short comment.
- **Walk through each example like you're narrating it out loud**, not just stating the key insight. Trace what actually happens when the code runs, step by step, in plain words — e.g. "when you call `greet()`, Python doesn't run `greet` directly — it runs `wrapper()` instead, because that's what the decorator swapped in." The goal is that after reading one example, the reader could predict what the code prints without running it.
- **After the examples, the topic should feel completely demystified** — if a beginner would still be fuzzy on how the pieces fit together, add a sentence or two connecting the dots explicitly, even if that means being slightly repetitive.

None of this should water down the practice questions — those still ramp all the way to genuinely hard, real-world problems. The contrast is intentional: as friendly and simple as possible on the teaching side, as real and challenging as possible on the practice side.

## Delivery

Default to replying inline in the conversation with markdown formatting. If the summary is long (a sprawling topic like asyncio or a full OOP overview) and the user seems likely to want to save/reference it later, offer to save it as a markdown file instead of forcing a long wall of text into the chat — but don't ask first, just use judgment and mention the option if you went inline.

## Multiple topics in one request

If the user asks for summaries of several topics at once (e.g. "give me summaries of decorators and generators"), produce a complete, separate structured summary for each one — don't merge them or shortcut the practice question count for either.
