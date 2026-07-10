# Safety Assessment: canvas-design Skill

**What I reviewed:** The `canvas-design` skill used by Claude to make posters, art, and designs as PDF or PNG files.

---

## What This Skill Does (In Simple Words)

This skill is like a recipe that tells Claude how to make art.

When I ask for a poster or design, the skill tells Claude to:

1. First, make up a "design philosophy" — basically an art style or theme, written down in a text file (.md).
2. Then use that style to actually draw/build the art, saved as a PDF or PNG file.
3. Use fonts from a folder on the computer to make the text look nice.
4. Try to make the final result look like it was made carefully by a skilled human artist.

It also tells Claude to hide a small, subtle hint about the topic inside the artwork, in a clever way — like an inside joke that only some people would notice, kind of like an artist signing their work in a hidden spot.

That's it. It does not do anything more complicated than that.

---

## What This Skill Touches

I checked this carefully. Here is what it uses and does NOT use:

**What it touches:**
- Text I give it (my request/instructions)
- Font files stored locally on the computer (in a folder called `canvas-fonts`)
- Creates output files only: `.md` (text), `.pdf`, and `.png` (image files)

**What it does NOT touch:**
- ❌ No internet or website calls
- ❌ No API calls to outside services
- ❌ No passwords, login info, or account credentials
- ❌ No access to my personal files, emails, or other private data
- ❌ Nothing gets sent anywhere outside of the conversation

In short: this skill only reads my request and local font files, and only writes new design files. It does not reach out to the internet or handle any sensitive information.

---

## Anything That Looked a Bit Odd

One small thing stood out, but it is not a safety or privacy problem — it's just a style choice in how the instructions are written:

- The instructions push very hard on making the art "look human-made" and not "look AI-generated," and they ask for a hidden, subtle reference to be worked into the art that most people wouldn't notice.
- This is a creative/design instruction, not something that affects my data or privacy. It doesn't send information anywhere or hide anything from me — it just affects the artistic style of the output.

I'm noting it here for transparency, but it does not change my trust in the skill.

---

## Do I Trust This Skill?

**Yes, I trust it, and I consider it safe to enable.**

Reasons:
- It has no way to connect to the internet or any outside server.
- It does not ask for or use any passwords, keys, or account access.
- It only works with files it creates itself (art and design files) plus fonts already on the computer.
- Nothing about my personal data leaves the conversation.

**My verdict: SAFE TO ENABLE** — this skill only makes pictures/designs and does not touch anything sensitive or send data anywhere.

---
