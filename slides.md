---
theme: slidev-theme-architectural-console
background: https://cover.sli.dev
title: The Effective Use of AI
class: text-center
drawings:
  persist: false
transition: slide-left
duration: 35min
label: TECHNOGISE
---

# The Effective Use of AI

::subtitle::
Practical AI workflows, context engineering, and agentic execution

::speaker::
Kush & Ajitem

::role::
&nbsp;

::ghostCode::
```
$ agent "Add pagination to GET /users — limit + offset, max 100 per page"

▸ Reading src/routes/users.ts …
▸ Applying patch: query params + validation (zod)
▸ Updating tests: users.pagination.spec.ts

✓ 3 files changed — ready to review
```

---
layout: center
---

# AI Landscape

![](./images/slide-1.png)

---
layout: statement
---

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
layout: default
---

# Expectations

ABC

---
layout: terminal
windowLabel: "agent session"
windowCommand: "upgrade-project --java 17"
---

::title::
The Moment AI <span class="ac-accent">stopped being a tool</span>

::default::
<div class="terminal-session-fit">
<div><span class="ac-term-prompt">></span> <span class="ac-term-cmd">Upgrade my project to Java 17</span></div>
<div class="ac-term-output">Thinking...</div>
<div class="ac-term-output">I need permission to update your project files: y/n</div>
<div><span class="ac-term-prompt">></span> <span class="ac-term-cmd">y</span></div>
<div class="ac-term-output">Thinking...</div>
<div class="ac-term-output">Detected Java 7 - upgrading to Java 17</div>
<div class="ac-term-output">Updating Gradle dependencies...</div>
<div class="ac-term-output">Refactoring deprecated APIs...</div>
<div class="ac-term-output">Running build checks...</div>
<div class="ac-term-success">Migration completed. Build is passing.</div>
<div class="ac-term-output">Summary:</div>
<div class="ac-term-output">- Code upgraded from Java 7 to Java 17</div>
<div class="ac-term-output">- Gradle upgraded from 1.9 to 8.5.1</div>
<div class="ac-term-output">- Deprecated methods replaced with upgraded contracts</div>
<div class="ac-term-success">WOW!! 😮</div>
</div>

<style>
:deep(.layout-terminal:has(.terminal-session-fit) .terminal-title) {
  padding-bottom: 0.5rem;
}
:deep(.layout-terminal:has(.terminal-session-fit) .terminal-title h2) {
  font-size: clamp(0.95rem, 2.5vw, 1.3rem);
  line-height: 1.12;
  margin: 0;
}
:deep(.layout-terminal:has(.terminal-session-fit) .terminal-body) {
  overflow: hidden;
  font-size: clamp(9px, 1.45vmin, 11px);
  line-height: 1.22;
  padding: 10px 12px;
}
</style>

---

# The Bittersweet Reality

##

The **WOW** moment fades fast! 😕

- Some people offload entire workflows to AI --- and it just works!
- Some spend 20 minutes rephrasing the same question.

Same tool. Wildly different results.

Why?

---
layout: statement
---

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
layout:default
---

# The Mindset Shift

ABC

---

# The Journey with Agents

What exactly is a "context"?

<v-click>
<blockquote>
Context is everything AI needs to not ask you a clarifying question.
</blockquote>
</v-click>

---
layout: statement
---

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
layout: default
---

# Ways to Build Context

ABC

---
layout: two-cols
---

# Same Tool, Different Outcomes

#### 🤔 Person A
Google -> ❌ Random results

<br/>

#### ⚡ Person B
Google -> ✅ Exact answer

::right::

- Same tool  
- Same access  
- Different outcomes  

<v-click>
<blockquote>It's not knowing AI. It's about how to <em>communicate</em> with it.
</blockquote>
</v-click>

---
layout: comparison-table
title: "Myth vs Truth"
subtitle: "Prompting discipline over prompt tricks"
columns:
  - "Myth"
  - "Truth"
rows:
  - criterion: "Prompt quality"
    values:
      - "Better prompts = better results"
      - "Better framing + context = better results"
    verdict: "Truth"
    verdictVariant: "info"
  - criterion: "Context amount"
    values:
      - "More context is always better"
      - "Relevant context > more context"
    verdict: "Truth"
    verdictVariant: "amber"
  - criterion: "Model understanding"
    values:
      - "AI understands what you mean"
      - "AI predicts patterns from training"
    verdict: "Truth"
    verdictVariant: "info"
---

## Myth vs Truth

---
layout: before-after
badPrompt: |
  #### Bad Prompt

  ```markdown
  Task: Convert a legacy `build.gradle` file to Gradle 8+ syntax and upgrade dependencies to Java 17-compatible versions.
  ```
goodPrompt: |
  #### Good Prompt

  ```markdown
  Task: Convert a legacy build.gradle file to Gradle 8+ syntax and upgrade all dependencies to Java 17 compatible versions
  only as specified below.

  ## Phase 0: General rules
  • **Constraint**: Do not add comments and try to replace dependencies in-line so they show up clearly in git diff
  • **Constraint**: Do not upgrade every dependency you think you should do in order to upgrade to Java 17.
  Stick to the ones mentioned here.
  • **Constraint**: Do not make any changes beyond current directory.
  • **Constraint**: If you find compilation errors after making the changes during the validation stage,
  wait before proceeding to fix those and ask for further inputs.

  ## Phase 1: Gradle Syntax Modernization

  ### 1. Update log4j dependencies:
  • Find all log4j dependencies (log4j-api, log4j-core, log4j-1.2-api)
  • Update version from any existing version to 2.23.1

  ### 2. Update Spring dependencies:
  • Find all Spring dependencies
  • Update version from any existing version to 6.2.7

  ## Phase 2: Structure Preservation and Validation

  ### 3. Preserve existing structure:
  • Keep all other dependencies unchanged
  • Maintain existing dependency scopes (compileOnly, implementation, testImplementation, etc.)
  • Preserve all non-dependency blocks (jar, java, test configurations)

  ### 4. Validation:
  • Ensure the build compiles successfully
  • Verify no functionality is lost in the conversion
  • Test with: gradle clean build -x test
  • Ensure Java 17 compatibility for all dependencies
  • Verify no breaking changes in functionality

  ### 5. Add Java tooling, if not there already
  java {
       toolchain {
           languageVersion = JavaLanguageVersion.of(17)
      }
   }

  ### 6. Add/Modify sourceSets based on project structure. Determine the value to go inside srcDirs.
  sourceSets {
      main {
          java {
              srcDirs = ['src/main']
          }
      }
  }

  ### 7. Remove metaInfDir task. Instead add metaInf { from ('src/main/META-INF') } under jar tag

  Expected outcome: A fully modernized build.gradle file compatible with Gradle 8+ that uses Java 17 compatible dependencies with
  official Maven coordinates, eliminating proprietary group IDs and deprecated libraries while maintaining all existing
  functionality.
  ```
---

# Good vs Bad prompt: Example 1

 Contrasts a single vague **Gradle 8 + Java 17** ask with a phased prompt: explicit **constraints**, pinned **dependency versions**, validation commands, and a clear **expected outcome**—so the model stays in scope instead of upgrading everything it can find.

::before::

<MarkdownContent :content="$frontmatter.badPrompt" />

::after::

<MarkdownContent :content="$frontmatter.goodPrompt" />

---

## Good vs Bad prompt: Example 2

TBA

---
layout: lesson-learned
---

::title::
Best Practices & <span class="ac-accent">Limitations</span>

<ol>
  <li>
    <span class="num">01</span>
    <div>
      <div class="item-title">Break problems down</div>
      <div class="item-desc">Avoid vague briefs like "refactor my code".</div>
    </div>
  </li>
  <li>
    <span class="num">02</span>
    <div>
      <div class="item-title">Trust, but verify</div>
      <div class="item-desc">AI can be confidently wrong; verify critical outputs.</div>
    </div>
  </li>
  <li>
    <span class="num">03</span>
    <div>
      <div class="item-title">Ask AI to plan first</div>
      <div class="item-desc">Review approach before execution.</div>
    </div>
  </li>
  <li>
    <span class="num">04</span>
    <div>
      <div class="item-title">Don't chase features</div>
      <div class="item-desc">Mindset beats tooling bells and whistles.</div>
    </div>
  </li>
  <li>
    <span class="num">05</span>
    <div>
      <div class="item-title">Don't over-engineer agents</div>
      <div class="item-desc">Natural language is the leverage, not rigid prompts.</div>
    </div>
  </li>
  <li>
    <span class="num">06</span>
    <div>
      <div class="item-title">Never paste sensitive data</div>
      <div class="item-desc">No credentials, PII, or proprietary code in public models.</div>
    </div>
  </li>
</ol>
