# Python Topic Summary Skill

A custom Claude skill that turns "explain X in Python" into a structured, self-contained study guide — no more hunting across docs, blog posts, and Stack Overflow answers just to learn one concept.

## The problem it solves

Learning a new Python topic (decorators, generators, asyncio, etc.) usually means piecing together information from scattered sources: one page for the definition, another for syntax, a tutorial for examples, and a separate site for practice problems. It's slow, and the explanations are rarely pitched at the right level — either too shallow or assuming knowledge you don't have yet.

This skill collapses all of that into a single response: a plain-language definition, real syntax, 2–3 real-life code examples with walkthroughs, and 10+ practice questions that ramp from beginner to expert. It's built for daily, casual learning — the kind of "let me understand this concept in the next 10 minutes" moment that comes up while studying or working through a course.

## Example prompts that trigger it

The skill fires automatically, without needing to name it explicitly — just ask for a topic naturally:

- "Summary of decorators"
- "Brief description of generators in Python"
- "Can you explain list comprehensions?"
- "Give me a rundown on asyncio"
- "Brief on *args and **kwargs"
- "Quick summary of context managers in Python"

It does **not** trigger for debugging or code-review questions that just sound related, e.g. "why is my decorator not working" — those get answered directly instead.

## What the output looks like

Every summary follows the same structure:

1. **Definition** — plain language, leads with *why* the concept exists before *what* it is
2. **Syntax** — the real patterns used in practice, not every obscure variant
3. **Real-life examples (2–3)** — genuine developer scenarios with step-by-step walkthroughs
4. **Practice questions (10+)** — a genuine difficulty ramp from "warm-up" to "expert-level," problems to solve rather than trivia

The teaching sections stay beginner-friendly throughout; the practice questions stay hard. That contrast is intentional.

## Notes

- Hints/solutions to practice questions are only given if explicitly asked for afterward — they're deliberately withheld by default.
- If a request doesn't specify a topic, the skill asks which one instead of guessing.
