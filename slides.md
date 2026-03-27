---
theme: architectural-console
background: https://cover.sli.dev
title: The Effective Use of AI
class: text-center
drawings:
  persist: false
transition: slide-left
duration: 35min
label: TECHNOGISE
colorSchema: light
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
layout: default
---

# Who is this for?

<v-clicks>

- <span v-mark="{ at: 1, type: 'highlight', color: '#22C55E' }">The believers</span> who've delegated half their workflow to it
- <span v-mark="{ at: 2, type: 'bracket', color: '#EF4444' }">The sceptics</span> who tried it once, got burned, and moved on
- <span v-mark="{ at: 3, type: 'circle', color: '#8fd5ff' }">The curious</span> who don't know where to start

</v-clicks>

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

* Some people offload entire workflows to AI --- and it just works!
* Some spend 20 minutes rephrasing the same question.

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
layout: center
class: mindset-hero-slide
transition: fade-out
---

<div class="mindset-hero">

<p class="mindset-hero__eyebrow">The mindset shift</p>

<v-click>
<p class="mindset-hero__false-start">
  <span v-mark.strike-through="{ at: 2 }" class="mindset-hero__strike">"Here's the codebase. Ship the feature."</span>
</p>
</v-click>

<v-click>
<p class="mindset-hero__truth">
  Week one is almost entirely <span v-mark.highlight="{ color: 'rgba(143, 213, 255, 0.35)' }">context transfer</span>.
</p>
</v-click>

<v-click>
<div class="mindset-hero__chips" aria-label="What day one actually looks like">
  <span>Domain</span>
  <span>Architecture</span>
  <span>Sign-off · autonomy</span>
  <span>Conventions · deploy · unwritten rules</span>
</div>
</v-click>

<v-click>
<p class="mindset-hero__law">
  Capability without context → <span v-mark.circle="{ color: '#EF4444' }">wrong output</span>
</p>
<p class="mindset-hero__same">Not because the consultant — or the model — is incapable.<br />Humans. AI. <span v-mark.box="{ color: 'rgba(34, 197, 94, 0.45)' }">Same rule</span>.</p>
</v-click>

<v-click>
<p class="mindset-hero__punch">The tool isn't the problem.</p>
<p class="mindset-hero__punch-accent"><span v-mark.underline="{ color: '#8fd5ff' }">The onboarding is</span>.</p>
</v-click>

</div>

<style scoped>
.mindset-hero-slide :deep(.slidev-layout.center) {
  justify-content: center;
  padding-top: 0;
}
.mindset-hero {
  max-width: 42rem;
  margin: 0 auto;
  text-align: center;
}
.mindset-hero__eyebrow {
  font-size: clamp(0.65rem, 1.2vw, 0.75rem);
  letter-spacing: 0.35em;
  text-transform: uppercase;
  opacity: 0.55;
  margin-bottom: clamp(1.25rem, 3vh, 2rem);
}
.mindset-hero__false-start {
  font-size: clamp(1.05rem, 2.2vw, 1.35rem);
  line-height: 1.45;
  opacity: 0.92;
  margin: 0 0 1.5rem;
}
.mindset-hero__strike {
  font-style: italic;
}
.mindset-hero__truth {
  font-size: clamp(1.15rem, 2.5vw, 1.5rem);
  line-height: 1.4;
  font-weight: 600;
  margin: 0 0 1.75rem;
}
.mindset-hero__chips {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5rem 0.65rem;
  margin: 0 auto 1.75rem;
  max-width: 36rem;
}
.mindset-hero__chips span {
  font-size: clamp(0.7rem, 1.35vw, 0.82rem);
  letter-spacing: 0.06em;
  text-transform: uppercase;
  opacity: 0.72;
  padding: 0.35rem 0.65rem;
  border: 1px solid rgba(255, 255, 255, 0.12);
  border-radius: 2px;
}
.mindset-hero__law {
  font-size: clamp(1.1rem, 2.2vw, 1.4rem);
  font-weight: 600;
  line-height: 1.35;
  margin: 0 0 0.85rem;
}
.mindset-hero__same {
  font-size: clamp(0.88rem, 1.65vw, 1.02rem);
  line-height: 1.55;
  opacity: 0.78;
  margin: 0;
}
.mindset-hero__punch {
  font-size: clamp(1.05rem, 2vw, 1.25rem);
  opacity: 0.75;
  margin: 1.75rem 0 0.35rem;
}
.mindset-hero__punch-accent {
  font-size: clamp(1.35rem, 3vw, 2rem);
  font-weight: 700;
  line-height: 1.2;
  margin: 0;
  letter-spacing: -0.02em;
}
</style>

<!--
HERO — take this slowly; the deck is sparse on purpose.

Technogise day one: contrast the false start on screen with how engagements really open — domain, why the architecture is the way it is, what needs approval vs what you can run with, conventions, deploy path, the unwritten rules. First week is context transfer.

Land: capability without context → wrong output, for people and for AI.

Close verbally with the multiplier line (also on the prior statement slide if you keep that order): if your value is writing code, AI is a threat; if it's solving problems, AI is a multiplier.

Optional beats to say, not show: "Write this function" vs naming the system, problem, constraints, and definition of done — richer context wins, not fancier prompts.

Three principles if you have time: context is the real prompt; iteration beats perfection; conversation beats commands.

Pause on the last click. Let "The onboarding is." hang.
-->

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

> "Articulating your system clearly is a core engineering discipline — and whether you're talking to a teammate or an AI, the clarity you bring in is the quality you get out."

---
layout: two-cols
---

# Ways to Build Context

<br/>
<v-clicks>
- Organise context: <span v-mark.highlight="{ color: 'rgba(143, 213, 255, 0.35)', at: 1 }">architecture docs,</span> <span v-mark.highlight="{ color: 'rgba(34, 197, 94, 0.25)', at: 2 }">coding style,</span> <span v-mark.highlight="{ color: 'rgba(245, 158, 11, 0.25),', at: 3 }">constraints</span>
<br/>
</v-clicks>
<v-click>
- Real skill: explain what you need <span v-mark.underline="{ color: '#8fd5ff', at: 5 }">clearly</span>
</v-click>
<br/><br/><br/>
<br/><br/><br/>
<v-click>
<blockquote>Tools help you organise context. Communication moves the needle.</blockquote>
</v-click>

::right::

<v-after>

### Agency Agents
[Open-source specialist agents](https://github.com/msitarzewski/agency-agents) you install into your coding tool. Assemble a team (frontend wizards, reality checkers, etc.) without building configs from scratch

<br/>

### OpenViking
[Open-source context database](https://openviking.ai) (L0/L1/L2) for an agent's memory as a filesystem. Load only the context you need; avoid fragmented vector storage and RAG black boxes

<br/>

### Impeccable
[Design vocabulary + skills](https://impeccable.style/) so agents can produce consistent UI/UX work. Turns “more vertical rhythm” into concrete, reusable design actions
</v-after>

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
<br/><br/>
<br/><br/>
<v-click>
<blockquote>It's not knowing AI. It's about how to <em>communicate</em> with it.</blockquote>
</v-click>

---
layout: default
---

# Myth vs Truth

<div v-click>

Better prompts = better results. --- ❌ Myth

</div>

<div v-click>

Better problem framing + context = better results. --- ✅ Truth

</div>

<br>

<div v-click>

More context is always better. --- ❌ Myth

</div>

<div v-click>

Relevant context > more context. --- ✅ Truth

</div>

<br>

<div v-click>

AI understands what you mean. --- ❌ Myth

</div>

<div v-click>

It generates responses based on patterns it has learned. --- ✅ Truth

</div>

---
layout: before-after
badPrompt: |
  #### Bad Prompt

  ```markdown
  Task: Convert a legacy `build.gradle` file to 
  Gradle 8+ syntax and upgrade dependencies to 
  Java 17-compatible versions.
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

::before::

<MarkdownContent :content="$frontmatter.badPrompt" />

::after::

<MarkdownContent :content="$frontmatter.goodPrompt" />

---
layout: before-after
before: |
  #### Bad Prompt

  ```
  gh can sometimes not be installed or not authenticated 
  with the right credentials. Can you fix it so it shows
  something when there's an error?
  ```
after: |
  #### Good Prompt

  ```
  Summary
  gh is listed as a hard requirement for PR and CI status. If it is not installed or not authenticated, gwaim silently returns empty PR fields on every worktree card with no explanation. A new user who has not yet run gh auth login will see blank PR sections and have no idea why. The tool should degrade gracefully — detect the missing or unauthenticated gh CLI, surface a clear message, and keep everything else functional.

  Current behaviour
  If gh is not installed:

  PR fields on all cards are silently empty.
  No error is shown.
  The tool continues to function but looks broken.
  If gh is installed but not authenticated:

  Same silent failure.
  CLAUDE.md mentions: “The gh CLI must be authenticated (gh auth login) or PR fetching silently returns no results.”
  This is documented for agents but completely invisible to end users.
  Expected behaviour
  If gh is not installed or not authenticated, gwaim should:

  Detect the condition at startup (or on first refresh).
  Show a clear, actionable message on the status bar or within the PR field of each card — e.g. PR status unavailable: run gh auth login or gh CLI not found.
  Continue operating normally for all other features (worktree listing, agent detection, sync status, create/delete/pull).
  Proposed implementation
  In internal/github/pr.go, wrap the gh invocation with a pre-flight check:

    ```go
    func isGhAvailable() error {
        _, err := exec.LookPath("gh")
        if err != nil {
            return fmt.Errorf("gh CLI not found: install from https://cli.github.com")
        }

        cmd := exec.Command("gh", "auth", "status")
        if err := cmd.Run(); err != nil {
            return fmt.Errorf("gh CLI not authenticated: run 'gh auth login'")
        }

        return nil
    }
    ```

  Return a typed error that the TUI can distinguish from a network or API error, and render it appropriately on the card or status bar.

  ## Acceptance criteria

  [] gwaim detects missing gh CLI at startup and shows a clear message
  [] gwaim detects unauthenticated gh CLI and shows an actionable message (gh auth login)
  [] All non-PR features continue to work normally when gh is unavailable
  [] PR card fields show a human-readable unavailability indicator rather than blank fields
  [] Detection runs once at startup (not on every refresh) to avoid performance overhead
  ```
---

::before::

<MarkdownContent :content="$frontmatter.before"></MarkdownContent>

::after::

<MarkdownContent :content="$frontmatter.after"></MarkdownContent>


---
layout: center
class: six-levels-slide
transition: fade-out
---

# The Six Levels

<v-click>
  <p class="six-levels__lead">
    The same skill, escalating autonomy: your <span v-mark.highlight="{ color: 'rgba(143, 213, 255, 0.30)' }">interface</span> changes every level.
  </p>
</v-click>

<div class="six-levels">
  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">1</span>
      <div class="six-levels__body">
        <div class="six-levels__label">No AI</div>
        <div class="six-levels__meta">You write everything by hand. The <span v-mark.underline="{ color: '#8fd5ff' }">IDE</span> drives navigation, refactors, debugging, tests.</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">2</span>
      <div class="six-levels__body">
        <div class="six-levels__label">Code completions</div>
        <div class="six-levels__meta">AI suggests the next block. You accept/reject—<span v-mark.box="{ color: 'rgba(143, 213, 255, 0.25)' }">inline</span>.</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">3</span>
      <div class="six-levels__body">
        <div class="six-levels__label">Chat agents in the IDE</div>
        <div class="six-levels__meta">You describe intent. The agent edits multi-line with <span v-mark.highlight="{ color: 'rgba(34, 197, 94, 0.25)' }">project context</span>.</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">4</span>
      <div class="six-levels__body">
        <div class="six-levels__label">One terminal coding agent</div>
        <div class="six-levels__meta">Reads/writes the repo, runs tests, iterates. The <span v-mark.circle="{ color: '#34d399' }">IDE</span> is your diff review surface.</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">5</span>
      <div class="six-levels__body">
        <div class="six-levels__label">Multiple agents in parallel</div>
        <div class="six-levels__meta">Each works a separate worktree/task. You supervise windows—less coding, more orchestration.</div>
      </div>
    </div>
  </v-click>

  <v-click>
    <div class="six-levels__row">
      <span class="six-levels__num">6</span>
      <div class="six-levels__body">
        <div class="six-levels__label">Agents run autonomously</div>
        <div class="six-levels__meta">CI/cloud on a schedule. You review pull requests. The trajectory is clear.</div>
      </div>
    </div>
  </v-click>
</div>

<style scoped>
.six-levels-slide :deep(.slidev-layout.center) {
  padding-top: 0;
}

.six-levels__lead {
  max-width: 56rem;
  margin: 0.2rem auto 1.1rem;
  opacity: 0.78;
  line-height: 1.4;
  font-size: 1.05rem;
}

.six-levels {
  max-width: 60rem;
  margin: 0 auto;
}

.six-levels__row {
  display: flex;
  gap: 1rem;
  align-items: flex-start;
  padding: 0.72rem 1rem;
  margin: 0.55rem 0;
  border-radius: 14px;
  border: 1px solid rgba(255, 255, 255, 0.12);
  background: rgba(255, 255, 255, 0.03);
}

.six-levels__num {
  width: 2.2rem;
  height: 2.2rem;
  border-radius: 999px;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  font-weight: 850;
  letter-spacing: -0.02em;
  color: rgba(143, 213, 255, 0.96);
  border: 1px solid rgba(143, 213, 255, 0.35);
  background: rgba(143, 213, 255, 0.10);
  flex: 0 0 auto;
}

.six-levels__body {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
}

.six-levels__label {
  font-weight: 700;
  opacity: 0.95;
  line-height: 1.2;
}

.six-levels__meta {
  opacity: 0.82;
  line-height: 1.35;
}
</style>

---
layout: lesson-learned
---

::title::
Best Practices & <span class="ac-accent">Limitations</span>

<ol>
  <li>
    <div>
      <div class="item-title">Break problems down</div>
      <div class="item-desc">Avoid vague briefs like "refactor my code".</div>
    </div>
  </li>
  <li>
    <div>
      <div class="item-title">Trust, but verify</div>
      <div class="item-desc">AI can be confidently wrong; verify critical outputs.</div>
    </div>
  </li>
  <li>
    <div>
      <div class="item-title">Ask AI to plan first</div>
      <div class="item-desc">Review approach before execution.</div>
    </div>
  </li>
  <li>
    <div>
      <div class="item-title">Don't chase features</div>
      <div class="item-desc">Mindset beats tooling bells and whistles.</div>
    </div>
  </li>
  <li>
    <div>
      <div class="item-title">Don't over-engineer agents</div>
      <div class="item-desc">Natural language is the leverage, not rigid prompts.</div>
    </div>
  </li>
  <li>
    <div>
      <div class="item-title">Never paste sensitive data</div>
      <div class="item-desc">No credentials, PII, or proprietary code in public models.</div>
    </div>
  </li>
</ol>
