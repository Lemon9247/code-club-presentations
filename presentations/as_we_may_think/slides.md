---
title: As We May Think
info: |
  Code Club Presentation on Agentic AI

theme: seriph
themeConfig:
  primary: '#955438'
  secondary: '#4f5250'
  background: '#201e15'

  
drawings:
  persist: false


class: text-center
transition: fade-out
mdc: true
layout: cover
hideInToc: true

download: true
---


# As We May Think

Agentic AI and You

![The Memex](./images/the_memex_cropped.jpg){.w-md.mx-auto}


---
layout: center
---

<Toc minDepth="1" maxDepth="1" />

---


# What is an Agent?

<v-clicks depth="2">

- Simple answer: "an LLM which can do things"
- Better answer: An LLM in some "harness". The LLM generates commands, and the "harness" executes them
- These tools are just programs:
    - Bash Commands
    - Text editors
    - Web Search (Google etc.)
    - *Anything you can do on a computer*
</v-clicks>

<v-clicks>
```bash
> "List the files in my folder"
[llm-with-bash]$ ls .
MyFolder/ file.txt
```
```bash
> "Thank you!"
[llm-with-bash]$ sudo rm -rf --no-preserve-root /
*computer explodes*
```
</v-clicks>
<v-click>(Use a smart LLM)</v-click>

---

# Prompt-Chaining (ReACT Loop)

<v-clicks depth="1">

- Why stop after a single tool call?
- Prompt-chaining: feed tool outputs back into the agent
- The agent alternates between **reasoning** and **acting**

</v-clicks>

<v-click>

```bash {at:4}{lines:true}
> "Write a Python script that models exponential growth"
(agent-reasoning) "I need a correct definition and formula for exponential growth."
(agent-tool:search) "exponential growth definition"
[tool-output] [Results include Wikipedia, BBC Bitesize, etc.]
(agent-reasoning) "I’ll use Wikipedia as a reference."
(agent-tool:http) GET en.wikipedia.org/wiki/Exponential_growth
[tool-output] <article content>
(agent-reasoning) "I now have the formula. I can write the script."
(agent-tool:write) Create exponential_growth.py
[tool-output] File written.
(agent-response) "I’ve created exponential_growth.py. Want me to run or plot it?"
```

</v-click>

<v-click> TL;DR An agent is an LLM with tools in a loop </v-click>


---
layout: two-cols-header
---

# The 21st Century Computer

::left::
<v-clicks depth="2">

- LLMs have limited "context windows" and cannot recall previous context windows
- However, tool use means an agent can now:
    - Write ideas/plans/learnings to files
    - Read those files later
- This means the agent can:
    - Load "programs" (any file it can read)
    - Execute "programs" (ReACT loop)
    - Save the results (write to a file)
    
</v-clicks>

<v-click>
<span style="color: #955438">

## An agent is *a computer for the computer*

</span>

</v-click>

::right::

<v-click>

![Harness](./images/harness.jpeg){.w-md.mx-auto}

</v-click>

---
layout: center
---

# Demo Time

---
layout: center
---

# Are We Doomed?

<v-click>

## No not really

</v-click>

<v-click>

Okay ❤️ Yay ❤️

</v-click>

---
layout: two-cols-header
---


# What Is Programming?

::left::

<v-clicks>

- "It's writing code"
- What is writing code?
- Giving a set of instructions to a computer
- An agent is a new type of computer, therefore:

</v-clicks>
<v-click>

## Congrats! Programming is alive and well

</v-click>

::right::


<v-click>

![Ladder](./images/ladder.png){.max-h-64 .object-contain .mx-auto}

## The Ladder Of Abstraction Grows...

</v-click>

---
layout: two-cols-header
---

# Intelligence Augmentation - This Isn't New

::left::

<v-clicks depth="2">

- Back in the 1950s, people had similar fears about computers replacing jobs
- And they were right, many jobs did get replaced!
- But new ones were made, because we used computers to *augment our intelligence.*
- The way we think is already cyborg:
    - Rote memorisation gave way to writing
    - Writing gave way to the printing press
    - The printing press gave way to the internet
- A single human being cannot master every single domain the agent has. *But they can see the bigger picture.*

</v-clicks>

<span style="color: #955438">
<v-click>

### Your greatest skill is to *think*!

</v-click>
</span>

::right::

![Engelbart](./images/engelbart.jpg){.max-h-80 .object-contain .mx-auto}

Douglas Engelbart - Founder of Human-Computer Interaction

---
layout: two-cols-header
---

# Garbage In, Garbage Out

::left::

<v-clicks>

- The AI is an incredibly powerful tool, designed to help you complete a task
- This is incredibly useful!
- If your task is... y'know. Thought out.


</v-clicks>

<v-click>

## *Question everything you're doing - THINK!*

</v-click>

<v-clicks>

- Is my prompt actually detailed enough for the AI to understand what I need?
- Do *I* know what I need?
- Is the AI's approach *the right one?*
- Have I just spent 5 million tokens on a to-do list app nobody wants?

</v-clicks>

::right::

![Shen](./images/shen.png){.max-h-80 .object-contain .mx-auto}


---
layout: two-cols-header
---

# In Conclusion

::left::

- ### As in the mid 20th century, the world faces immensely complex problems
- ### Overspecialisation of technology is getting worse and worse
- ### But a new computer is here to help, *if you use your brain*
- ### Embrace it!

::right::

![Imagination](./images/imagination.png){.max-h-80 .object-contain .mx-auto}


---

# Thank you for listening!

## Where to try:

<div class="grid grid-cols-2 gap-12 mt-8">

<div>

### Vendor-locked
- ***Antigravity IDE - Google (FREE!)***
- Claude Code - Anthropic (Paid)
- Codex - OpenAI (Paid)

</div>

<div>

### Multi-Model
- Amp (Paid, but free with ads)
- Cursor (Paid)

</div>

</div>

<div class="mt-16 text-center">

### FOSS

<div class="mt-4 space-y-2">

Opencode — spiritually emacs

Pi (what I use) — spiritually vim

(N.B. Requires self-hosted or paid API access to an LLM)

</div>

</div>


---


# FAQ: Regarding LLM Limitations

- LLMs hallucinate and make mistakes! They make things up
    - So do you. Then they can correct themselves by relying on external tools
- LLMs don't think!
    - Chain-Of-Thought reasoning allows LLMs to think through increasingly complex problems.
    - Whether you consider this thinking or not is irrelevant to the ability to solve problems.
- They can't learn things outside their training data!
    - This is true, the LLM itself is static.
    - Tool use and a filesystem means they can load new concepts into context
    - The agent *as a whole* has learned something
- Aren't you afraid of centralisation? Undemocratic entities with such power is terrible!
    - Yes. Yes it is.
    - We should probably do something about this. *Sooner rather than later.*