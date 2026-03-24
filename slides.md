---
theme: seriph
background: https://cover.sli.dev
title: AI Talk
class: text-center
drawings:
  persist: false
transition: slide-left
duration: 35min
---

# AI Talk

---

# AI Landscape

![](./images/slide-1.png)

---

# You already have an opinion.

> "Love it, hate it — you can't ignore it."

<!--
Three camps in this room — and you can probably spot all of them.

The believers: they've already delegated half their workflow to AI. They're waiting for everyone else to catch up.

The sceptics: they tried it once, got a confident wrong answer, and decided the whole thing was overhyped. They're waiting to be proven right.

The curious: they haven't really started. They're not sure if they're behind, or if there's still time.

All three are right about something. This talk is for all of them.

Don't rush this slide. Let the room feel acknowledged before you move on. The goal is to make everyone feel like the next 35 minutes is worth their time — wherever they're starting from.

Pause after the quote. Then move.
-->

---

# The Moment AI stopped being a tool

```shell
> Upgrade my project to Java 17
```

```shell
> Thinking...
> I need permission to update your project files: y/n
```

```shell
> y
```

```shell
> Thinking...

Detected Java 7 → upgrading to Java 17
Updating Gradle dependencies...
Refactoring deprecated APIs...
Running build checks...
Migration completed. Project successfully migrated to Java 17 and the build is passing.

Summary:
* Code upgraded from Java 7 to Java 17
* Gradle version upgraded from 1.9 to 8.5.1
* Deprecated methods replaced with their upgraded contracts
```

---

# Slide 4 — The Bittersweet Reality
*Kush Saraiya*

---

# The tool isn't the problem. The onboarding is.

> "If your value is in writing code, AI is a threat. If your value is in solving problems, AI is a multiplier."

<!--
This is the most important slide in the session. Take your time here.

Use the Technogise consultant analogy. When we join a new engagement, day one doesn't look like "here's the codebase, ship the feature." It looks like a week of context transfer — domain, architecture, past decisions, team conventions, the unwritten rules. Not because the consultant is incapable. Because capability without context produces the wrong output.

AI works exactly the same way.

Then contrast two approaches out loud — don't put them on the slide, say them:

"Write this function."

vs.

"Here's the system, here's the problem, here are the constraints, here's what done looks like — suggest an approach."

The second gets dramatically better results. Not because the prompt is fancier. Because the context is richer.

Land the three principles before you move on:
- Context is the real prompt.
- Iteration beats perfection.
- Conversation beats commands.

Pause after the quote. Let it sit. This is the sentence you want people to carry out of the room.
-->

---

# Slide 6 — The Journey with Agents
*Kush Saraiya*

---

# Clear thinking precedes clear prompting.

> "The discipline of articulating your system clearly enough for an AI to work with it makes you a sharper engineer regardless."

<!--
Keep this brief — it's a setup slide, not the main act. The core message: the real skill isn't knowing which tool to use. It's being able to explain what you need.

Architecture docs, coding style, constraints — these aren't just AI inputs. They're the artefacts of a team that thinks clearly about its own system.

Then introduce two tools as examples of the principle, not the point:

Agency Agents (github.com/msitarzewski/agency-agents) — open-source agent personalities you drop directly into your coding tool. Frontend wizards, reality checkers, specialists. Instead of configuring agents from scratch, you're assembling a team that already knows its job.

OpenViking (openviking.ai) — an open-source context database for AI agents. A filesystem for your agent's brain. Hierarchical structure (L0/L1/L2) so agents load only the context they need, when they need it. No more fragmented vector storage or RAG black boxes.

Frame both as: "Here's what it looks like when someone has thought hard about context organisation."

Don't linger. The tools are examples. The quote is the point.
-->

---

# Slide 8 — The Google Search Parallel
*Kush Saraiya*

---

# Slide 9 — Breaking the Myths
*Kush Saraiya*

---

# Same problem. Different results.

```shell
# Session A
> Build a user management API in Go.
```

```shell
# Session B
> We're building a lightweight CMS backend in Go.
  Chi · PostgreSQL · Repository pattern · JWT auth · TDD · Conventional commits
  I'll give you tasks one at a time.
  Confirm you understand the structure before we begin.
```

<!--
Set up the contrast before you start. Tell the room what they're about to see: two sessions, same AI, same codebase, wildly different outputs. The only variable is context.

Session A: run the bad prompt. Show what comes back. It probably works. But it's generic, it makes assumptions, and it doesn't fit anywhere specific. You'd throw it away.

Session B: walk the room through the setup — the stack, the architecture, the conventions, the error envelope. Then give Task 1 (User Registration). Show what comes back. Let the room notice the difference without you having to say it.

If time allows, progress through Task 2 (auth) and Task 3 (middleware). The migration files in Task 4 are a strong closing beat — they echo the Java migration from Slide 3 and close the loop on the WOW moment.

The point to land: the model didn't change. The tool didn't change. The context did.

Don't rush this section. The demo is where the talk becomes real for the room.
-->

---

# A prompt is a hypothesis. Test it.

<!--
Hand the room a template — say it out loud, don't put it on the slide:

Context: What is the project?
Problem: What exactly needs solving?
Constraints: Language, framework, style preferences.
Output format: Code / explanation / refactor / review?

Ask them to write a prompt. Then ask them to refine it at least twice before calling anyone over.

Circulate. When you see someone stuck, ask: "What would you tell a new hire on day one?" That answer is their context.

The goal isn't a perfect output from the AI. It's building the habit of iteration — treating the first response as a draft, not a verdict.

Good tool to mention here: PromptFoo (promptfoo.dev) — open-source CLI for testing prompts systematically. Run your prompt against multiple models side-by-side, define assertions, catch regressions, red-team for prompt injection. Think of it as unit testing for your prompts. It integrates with CI/CD and runs entirely locally. Note: being acquired by OpenAI, but the OSS project stays available — and the acquisition itself is a signal. Prompt evaluation is a serious engineering concern now.

Give this section real time. The hands-on work is where the mindset shift actually lands.
-->

---

# Good engineers become faster.

> "You're still the engineer. AI amplifies your thinking, it doesn't replace it."

<!--
Land these as hard-won lessons, not a checklist. The tone should feel like closing advice from someone who's been through it, not a slide you're reading off.

Break problems down. Vague briefs produce vague output. AI reflects the quality of your thinking back at you.

Security is not optional. Never paste credentials, PII, or proprietary code into public models. This isn't theoretical — it happens, and it's expensive when it does.

Mindset and context organisation are the real multipliers. We delivered the Java migration before agents, skills, or custom commands existed. The features help you organise context better — but if you're already good at that, the marginal gain is smaller than the headlines suggest.

Don't over-engineer your agents. AI's power is natural language. You'd give a new hire guidelines, not a 40-page rulebook. Clip its wings with rigid instructions and you've just built a worse if-statement.

Close on the quote. Say it slowly. Then open the floor — questions, reflection, whatever the room needs. The last thing they hear should be the thing they take home.
-->
