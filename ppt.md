# How to Create a PPT Using AI + Python
*A quick guide for understanding the efficient way*

---

## The Simple Idea

Most people directly ask AI:
> *"Create a PPT on databases"*

This works — but it's messy, costly, and hard to edit later.

**The better way:**
> First ask AI to **build a good prompt** → Then use that prompt to **generate slide content** → Then use a **Python script to build the actual PPT**

---

## Steps to Follow

### Step 1 — Give your raw idea to AI

Just tell the AI what you want in plain language. Don't worry about structure yet.

**Example:**
> *"I want to create a PPT on databases. Topics: SQL, NoSQL, Cache, Time Series. Session is 30 minutes. Audience is mostly non-technical managers."*

---

### Step 2 — Ask AI to generate a proper prompt (not the PPT yet)

This is the key step most people skip.

Tell the AI:
> *"Don't create the PPT yet. First, generate a well-structured prompt for this PPT that I can reuse or improve."*

The AI will now return a refined prompt like:
- Role defined (e.g., Staff Engineer with 15 years experience)
- Audience ratio mentioned (70% non-technical)
- Slide rules, tone, design preferences
- Output format specified

---

### Step 3 — Review and adjust the prompt

At this point, the AI may also ask you a few questions like:
- What is the audience mix? (Technical / Non-technical / Mixed)
- How long is the session?
- What color scheme or design style do you prefer?
- Should speaker notes be included?

Answer these — it makes the final output much better.

---

### Step 4 — Use the refined prompt to generate slide content

Now paste the refined prompt back into the AI (same or new session).

Ask it to return the slide content as **JSON format** — this is important for the Python step.

> *"Using the above prompt, generate the slide content. Return it as a JSON array with: slide_number, title, bullets, speaker_notes."*

---

### Step 5 — Run the Python script to build the PPT

Take the JSON output from Step 4 and feed it into a simple Python script.

The script will:
- Create the `.pptx` file automatically
- Apply your colors, fonts, and layout
- Add speaker notes to each slide
- Be done in under **3 seconds**

---

## Generic Prompt Structure (Reference)

Use this as a starting template whenever you want to create any PPT:

```
You are a [Role — e.g., Staff Engineer / Senior Consultant].

AUDIENCE:
- Primary: [e.g., 70% non-technical managers]
- Secondary: [e.g., 30% developers]
- Knowledge level: [Beginner / Mixed / Advanced]

SESSION:
- Duration: [e.g., 30 minutes]
- Goal: [What should the audience understand or do after this?]
- Tone: [Formal / Simple / Conversational]

TOPIC: [Your topic]

SECTIONS TO COVER:
1. [Topic 1]
2. [Topic 2]
3. [Topic 3]

SLIDE RULES:
- Max 4 bullets per slide
- Use simple analogies for complex topics
- Add speaker notes with deeper explanation

DESIGN:
- Color: [e.g., Deep Blue + White]
- Style: [Minimal / Corporate]

OUTPUT:
- Return as JSON array
- Keys: slide_number, title, bullets[], speaker_notes
```

---

## Why Python Script Is More Efficient

| Situation | Asking AI directly | Using Python script |
|---|---|---|
| Build a 15-slide deck | High token usage | AI gives JSON once, script builds instantly |
| Change slide color | Re-prompt AI again | Edit one line in the script |
| Fix a typo | Re-prompt or copy-paste | Edit the JSON file directly |
| Reuse for a new topic | Start from scratch | Reuse the same script, change only content |
| 50-slide deck | Very expensive | Same script, same speed |

**Bottom line:** AI is used only once — for thinking and content. Python handles all the building and formatting. Any small changes can be done without touching AI at all.

---

## Quick Summary

```
Your idea
   ↓
Ask AI to generate a prompt first (not the PPT)
   ↓
Review / answer a few questions
   ↓
Use refined prompt → Ask AI for JSON slide content
   ↓
Run Python script → Get your PPT file ✅
```
