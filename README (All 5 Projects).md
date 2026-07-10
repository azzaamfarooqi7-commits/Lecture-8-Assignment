# Summary of all five projects created by : Muhammad Azzaam

# Project 1 – Python Topic Summary Skill

## What this project is

This is a custom "skill" I built for Claude. A skill is basically a set of instructions I write once, and after that, Claude follows those instructions automatically whenever I ask for a certain kind of thing.

What my skill does: whenever I ask for a "summary" or "brief description" of a Python topic (like decorators, generators, list comprehensions, etc.), Claude gives me back a full study guide for that topic. It always includes:

- A simple, easy definition of the topic
- The actual Python syntax for it
- 2-3 real-life code examples, explained step by step
- At least 10 practice questions that start easy and slowly get harder, all the way up to expert-level problems

## AI tools and apps I used

- **Claude** (claude.ai chat) – this is the AI I used for the whole project
- **skill-creator** – a built-in Claude skill that helps you build your own custom skills. I used this to build my Python summary skill.

## The prompts I used (and how I improved them)

**First prompt:**
I asked Claude to use the skill-creator skill to build me a Python topic summary skill. I explained that whenever I ask for a "summary" or "brief description" of a Python topic, it should give me a definition, the syntax, a few real examples, and at least 10 practice questions going from beginner to expert level. I also said the tone should be beginner-friendly.

Claude asked me a few quick questions first, like:
- Do I want the summary shown in the chat or as a downloadable file?
- Do I want hints/answers with the practice questions?
- How many examples do I want per topic?

I answered:
- No strong preference on delivery
- Only give hints/answers if I actually ask for them
- 2-3 examples is enough

**Testing prompt:**
Claude then tested the skill on its own using "decorators" as an example topic, and showed me the result before finishing anything.

**My refinement:**
When I saw the first test result, the explanations felt a bit too advanced, like something written for someone who already knew Python well. So I told Claude:

> "The tone feels too expert level, keep it extremely beginner friendly and give easy-to-understand examples in such a way that after reading those examples, the topic must be crystal clear."

Claude rewrote the instructions so that every example is explained step by step, like it's talking me through exactly what happens when the code runs, using simple comparisons (like calling a decorator "gift-wrapping a function"). It then ran the same "decorators" test again with the new version so I could compare both.

## How I tested it

I didn't just take Claude's word for it — I actually read through the test output myself both times:

1. **First test (before feedback):** Claude generated the full "decorators" summary. It had all the right sections, but the writing style was too advanced for a beginner.
2. **Second test (after feedback):** Claude regenerated the same "decorators" summary using the updated, simpler tone. This time each example had a clear "step by step, what actually happens" walkthrough, and the topic genuinely made more sense after reading it.

Once I confirmed the second version was good, Claude packaged the finished skill into an installable file.

## What worked, what didn't, and problems I faced

**What worked:**
- The structure (definition → syntax → examples → practice questions) came out exactly the way I wanted.
- The practice questions really do ramp up properly — the first few are easy, and the last couple feel like real interview-level problems.
- Once I gave feedback about the tone, Claude fixed it in one go and the difference was clear.

**What didn't work at first:**
- The very first version of the explanations was too "expert-sounding" for someone still learning Python. I had to explicitly ask for simpler, more beginner-friendly wording with clearer examples.
- When Claude tried to package the finished skill into a file, it hit an error because the folder it tried to save into was read-only. Claude fixed this by copying the necessary files into a different folder first, and then it packaged successfully.

**Problems faced:**
- Mostly just the tone issue above — nothing major broke, it just needed one round of feedback to get right.

## Why I chose this skill and how it helps me

I'm currently learning Python, and one thing I kept running into is that a lot of explanations online (or even from AI) either move too fast or use words I don't fully understand yet. So I built this skill to solve that exact problem for myself.

Now, whenever I hit a new Python topic I don't understand, I can just say "summary of [topic]" and get:
- A simple explanation in plain English
- Real examples that are actually explained, not just shown
- Practice questions so I can test myself and slowly build up to harder problems

This basically turns Claude into a personal Python tutor that always explains things the way I actually need them explained, and it saves me from having to dig through confusing documentation or tutorials every time I get stuck on a new concept.

---

# Project 2 – Connecting App and Retrieving Data

## What This Project Is About
For this project, I connected my Gmail account to Claude using Anthropic's connector feature. The main idea was to test if Claude could actually reach into my real Gmail data (not just talk about Gmail in general) and pull out something specific — in this case, the very oldest email thread in my inbox, along with a short description of what that email was about.

So this project was really about two things:
1. Setting up and connecting Gmail as a connector to Claude.
2. Using that connection to retrieve and read real data from my account.

## AI Tools and Apps I Used
- **Claude** (chat interface) — the main AI tool I used to do the task.
- **Gmail connector** — I connected my Gmail account to Claude so it could search and read my actual emails.

## The Prompt I Used
I kept it simple and just asked directly:

> "Find the oldest email thread in my Gmail and give a brief description about the email"

I didn't need to refine this prompt much because it worked well on the first try. Claude understood that I wanted:
- The single oldest email in my whole mailbox (not just the oldest in some folder or label)
- A short summary of what that email was about, not the entire raw email dumped on me

## How I Tested/Verified It Worked
- I checked that Claude actually searched through my Gmail using the connector (it wasn't just guessing or making something up).
- I looked at the date it gave me and made sure it made sense as the oldest email compared to how long I've had the account.
- I double-checked the description matched what I expected — the email was about a PUBG Mobile gameplay video, which I remembered sending, so that gave me confidence it found the real, correct email.

## What Worked
- The Gmail connector worked properly and let Claude actually go into my inbox and search real data.
- Claude found the correct oldest email accurately.
- The description Claude gave back was short, clear, and matched the real email content.

## What Didn't Work / Problems I Faced
- Nothing majorly broke, but Claude had to try a few different date ranges behind the scenes to actually narrow down to the oldest email, since Gmail doesn't have a simple "sort by oldest" option built into search.
- I also learned that just typing "the oldest email" isn't 100% precise on its own — Claude had to interpret it correctly as "the very first email ever received/sent," so I had to trust it got the right one rather than one that just looked old.

## Final Thoughts
Overall this project showed me that connecting Gmail to Claude actually works — it's not just a chatbot answering from memory, it can genuinely search and pull real information from my own account when I give it a clear, simple instruction.

---

# Project 3 – Skill and Connector Used Together

## What This Project Is About
This project was about testing if Claude could combine two things at the same time: my connected Gmail account (connector) and a custom skill I built earlier (the Python Topic Summary skill). Instead of just fetching an email, I wanted to see if Claude would notice that an email was about a Python topic and automatically use my skill to turn it into a proper study summary — without me having to tell it to use the skill by name.

The email that ended up being used was a course enrollment confirmation from UniAthena, confirming I signed up for a course called "Basics of NumPy." Claude picked up on this being a Python-related topic and used my skill to explain NumPy in a structured way, with a definition, examples, and practice questions.

So really, this project shows the connector (Gmail) and the skill (Python Topic Summary) working together in one single request.

## AI Tools and Apps I Used
- **Claude** (chat interface) — the AI tool I used for the whole task.
- **Gmail connector** — used to search and read real emails from my inbox.
- **Python Topic Summary skill** — a custom skill I made earlier, used to turn the topic found in the email into a full study guide.

## The Prompts I Used
First prompt:
> "Pull another different email thread from my Gmail which contains any topic of python and give me an overview of that topic"

At first, Claude gave a good overview but treated it more like a general explanation rather than actually pulling a real topic overview using my skill. So on an earlier attempt in this same chat, I had to correct it and say something like:

> "you were actually supposed to use the python topic summary skill without me directly mentioning that you have to use this skill"

This refinement mattered a lot, because it reminded Claude that the skill should trigger automatically just from the context of the email, not only when I say the skill's name directly. After that correction, Claude applied the skill properly.

## How I Tested/Verified It Worked
- I checked that Claude actually searched my real Gmail inbox and found a real email (the UniAthena NumPy enrollment email), not something made up.
- I compared the topic in the email (NumPy) with the topic Claude explained — they matched.
- I checked that the explanation followed the structure of my skill (definition, syntax, examples, and practice questions), which confirmed the skill was actually triggered and not just a random explanation.

## What Worked
- The Gmail connector successfully found a different, new email thread related to Python (the NumPy course email).
- Once I corrected Claude, it correctly triggered my custom skill on its own for future similar requests, based only on the topic of the email — without me naming the skill.
- The final summary followed my skill's exact format (definition, syntax, real-life examples, and tiered practice questions).

## What Didn't Work / Problems I Faced
- The first attempt didn't fully use my skill — Claude gave a decent explanation, but it wasn't following the skill's format properly. I had to point this out directly before it corrected itself.
- This showed me that just because Claude *can* detect a topic doesn't mean it will automatically remember to use a specific custom skill unless it's guided once or the intent is made clear.

## Final Thoughts
This project proved that connectors and skills can work together — Claude can find real data from my Gmail and then apply my own custom skill on top of that data automatically, once it understands the pattern I want. It took one correction to get it fully right, but after that it worked exactly as intended.

---

# Project 4: Skill Handed Off

## What this project is about

For this project, I wanted to test something simple but important: can my Python Topic Summary skill work for someone else, on a different AI tool, without me explaining anything?

I had already built a skill that takes any Python topic (like decorators, list comprehensions, or generators) and turns it into a beginner-friendly study guide. It gives a simple definition, real code examples, and practice questions that go from easy to expert level.

But a skill that only works when I use it isn't really a finished asset. It's just a personal trick. So the real test was: if I hand this skill to someone else, with zero extra explanation from me, will they get the same good result I get?

That's what "Skill Handed Off" means — I'm proving the skill can survive outside my own head and outside my own conversation.

## Tools and apps I used

- **Claude** – where I originally built and tested the skill.
- **ChatGPT** – the platform my friend used to test the skill I handed off.
- The skill file/folder itself, which I sent directly to my friend.

## How I shared it

I didn't write my friend any instructions or tips on how to use it. I just sent them the skill file/folder and asked them to upload it and try it on a Python topic of their choice. No walkthrough, no "here's how it works" message. The goal was to see if the skill could explain itself.

## How I tested it

1. I packaged the skill exactly as I use it myself.
2. I sent the file to my friend with no extra explanation.
3. I asked them to upload it into ChatGPT and pick any Python topic to summarize.
4. I asked them to send me back what the tool gave them.
5. I compared their output to what I normally get when I run the skill myself, checking for:
   - A clear, beginner-friendly definition
   - Real working code examples
   - Practice questions that start easy and get harder (up to expert level)
   - No hints unless asked for (since that's how the skill is supposed to behave by default)

## What happened

It worked on the first try. My friend uploaded the skill to ChatGPT, ran it on a topic, and got a properly structured summary — definition, examples, and a full set of practice questions ramping up in difficulty. No extra input from me was needed, and no hints showed up unless they were asked for.

## What worked

- The skill triggered and behaved correctly on a completely different platform (ChatGPT instead of Claude).
- My friend didn't need any explanation from me to use it.
- The output matched the same structure and quality I get when I use it myself.
- The beginner-friendly tone and expert-level practice questions both came through as intended.

## What didn't work / problems I faced

Honestly, nothing broke. The handoff worked cleanly the first time. If anything, the "problem" was in my own head before testing — I wasn't sure a skill built with Claude in mind would behave the same way on a different AI tool. That worry turned out to be unfounded.

## Conclusion

This project confirms that my Python Topic Summary skill isn't a one-off trick that only works because I know how to prompt it. It's a real, reusable asset. Someone else, with no help from me, on a completely different platform, got the exact same quality of result. That's the proof I was looking for.

---

# Project 5: Auditing a Skill Before Trusting It

## Project Title and What It Does

This project is about checking a Skill before deciding if it is safe to use.

For this project, I installed the **canvas-design Skill** from the official skills directory. This Skill is used to create posters, art, and designs as PDF or PNG files.

Before trusting any new Skill, I wanted to know exactly what it does, what it touches, and if it could send my data somewhere it shouldn't. So I asked Claude to explain the Skill and check it for me, almost like doing a small safety inspection before letting it run.

The end goal was to write down my findings in plain English, so that even someone with no coding knowledge could read it and understand if the Skill is safe.

---

## AI Tool(s) and App(s) I Used

- **Claude** (chat interface) — I used Claude to read through the Skill's files and explain what it does in plain English.
- The **canvas-design Skill** itself, which is one of the official built-in Skills.

I did not use any other outside tool for this project. Everything was done directly through conversation with Claude.

---

## The Prompts I Used (and How I Refined Them)

I did not write one long prompt. Instead, I asked step by step, building on each answer:

1. First prompt:
   **"Expain what the canvas design skill does?"**
   This was just to get a basic understanding of what the Skill is for.

2. Second prompt (after reading the explanation):
   **"Flag anything sensitive and does this skill contact any external server, handle credentials, or send my data anywhere unexpected?"**
   This was the important safety question. I wanted a clear yes/no type answer about data and security, not just a general description.

So my prompting went from general → specific. Each step built on the last answer instead of me writing one big prompt at the start.

---

## How I Tested or Verified That It Worked

I did not run the Skill's code myself. Instead, I verified it by asking Claude to actually open and read the Skill's real files (not just guess from memory), and explain back to me:

- What the Skill's instructions actually say
- What files it creates
- Whether it mentions calling the internet, using APIs, or handling credentials anywhere in its instructions

I trusted this because Claude looked directly at the Skill's file content before answering, instead of just giving a general opinion. I also asked the sensitive-data question separately, as a kind of "double check," to make sure nothing was missed in the first explanation.

---

## What Worked, What Did Not, and Problems I Faced

**What worked:**
- Claude was able to clearly explain what the Skill does in normal, easy words.
- When I asked about safety, Claude gave a clear answer: no internet calls, no credentials used, no data sent anywhere outside the conversation.
- Claude also pointed out one small odd thing on its own (the Skill asks for a "hidden creative reference" in the artwork) even though I didn't specifically ask about that. I liked that it flagged this extra detail instead of only answering exactly what I asked.

**What did not work / problems I faced:**
- I had to be specific in my question ("does it contact any external server, handle credentials, or send my data anywhere unexpected") to get a real safety answer. A general question like "is this safe?" probably would not have given me as clear or detailed of an answer.

**Overall:**
This project taught me that before trusting any Skill, it is worth asking direct questions about data, servers, and credentials, instead of just asking "what does it do." The direct questions gave me a much clearer and more useful answer.
