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

# Slide 2 — Expectations
*Ajitem Sahasrabuddhe*

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

## WOW!! 😮

---

# The Bittersweet Reality

##

The **WOW** moment fades fast! 😕

- Some people offload entire workflows to AI --- and it just works!
- Some spend 20 minutes rephrasing the same question.

Same tool. Wildly different results.

Why?

---

# Slide 5 — The Mindset Shift
*Ajitem Sahasrabuddhe*

---

# The Journey with Agents

What exactly is a "context"?

<v-click>
<blockquote>
Context is everything AI needs to not ask you a clarifying question.
</blockquote>
</v-click>

---

# Slide 7 — Ways to Build Context
*Ajitem Sahasrabuddhe*

---

# Same Tool, Different Outcomes

<div class="grid grid-cols-2 gap-8 items-center mt-8">

<div>

#### 🤔 Person A
Google → ❌ Random results

<br/>

#### ⚡ Person B
Google → ✅ Exact answer

</div>

<div>

- Same tool
- Same access
- Different outcomes

</div>

</div>

<br>
<br>

<v-click>
<blockquote>It's not knowing AI. It's about how to <em>communicate</em> with it.
</blockquote>
</v-click>

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

# Good vs Bad prompt: Example 1

#### Bad Prompt

Task: Convert a legacy build.gradle file to Gradle 8+ syntax and upgrade all dependencies to Java 17 compatible versions.

#### Good prompt

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

# Good vs Bad prompt: Example 2
*Ajitem Sahasrabuddhe*

---

# Best Practices & Limitations

##

✅ Break problems down

##### Don't hand AI a vague brief like "refactor my code".

✅ Trust, but verify

##### AI is confident even when wrong. Always verify critical outputs.

✅ Ask AI to plan first

##### Ask for a plan of action before the solution. Review, refine, then execute.

✅ Don't chase features.

##### We delivered the Java migration before skills, agents, or custom commands existed. Mindset > Features.

✅ Don't over-engineer your agents

##### AI's power is natural language. Don't clip its wings with essays of rigid instructions.

✅ Never paste sensitive data

##### No credentials, PII, or proprietary code into public models.
