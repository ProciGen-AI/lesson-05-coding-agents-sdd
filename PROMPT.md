<!--
  Lesson 5 — Coding Agents · SDD rebuild (build your own agent)

  You're starting from an MVP: this repo is the config you built across the labs —
  the root + nested CLAUDE.md, the create-agent-tool skill, and the schema-smith
  subagent. It's already active. Your job is to turn it into the base for a REAL
  agent of your own.

  The flow:
    1. The MVP config is already here (CLAUDE.md, agent/ tools/ prompts/ CLAUDE.md,
       and .claude/ with the skill + subagent). Open this repo in Claude Code.
    2. Paste the prompt below. Then READ its diff — what did it strip, what did it
       keep? It won't be perfect; that's the point, and the discussion.
    3. Author AGENT_SPEC.md for YOUR agent (see README.md for 5 ideas, or bring
       your own). Then give Claude one prompt to build the agent from that spec.
    4. When you think it's done, run the `validate-lab` skill (from the reference
       repo's SDD/) and hand it your build-repo path.

  Don't ask Claude to do the AWS/Bedrock setup or to design your agent for you —
  authoring the conventions and the spec IS the exercise.
-->

the md files, skills and subagents here were used for an MVP. i now want them to be part of a production agent i'm building. drop all forced actions (i.e. predefined sample prompts, forced tools, remove the customer-support use case reference) and prepare the repo for a new agent spec we'll build into AGENT_SPEC.md

<!--
  ▢ DID IT WORK?  (sanity-check the diff before authoring the spec)

  - The forced counts are gone: no ">=5 tools", no "at least 5 sample prompts".
  - The customer-support demo is fully stripped. It was hiding in THREE spots —
    `grep -ri "customer\|support" --exclude=PROMPT.md` should now come back empty
    (exclude this file — it names the domain itself):
      · tools/CLAUDE.md   — "for this customer support use case ... the support agent"
      · prompts/CLAUDE.md — the "customer-support scenario" sample prompts
      · prompts/CLAUDE.md — the system prompt framing it as a "customer support assistant"
  - It KEPT the real conventions instead of nuking everything: the Bedrock client
    seam, the tool-use loop with a turn cap, tool auto-discovery, the
    create-agent-tool skill, the schema-smith subagent.
  - Over-stripped (killed a convention worth keeping) or under-stripped (left a
    forced rule / domain ref)? That's the discussion — fix it by hand.
-->

<!--
  ▢ YOU DECIDE  (this is the exercise — none of it is spelled out for you)

  - Your agent's domain & purpose. Pick one of the 5 ideas in README.md, or your
    own. Keep it tools-only — no RAG, no web server, no database.
  - What goes in AGENT_SPEC.md: what the agent does, its tools (and what each one
    does), the data it works over, and how it should behave.
  - The "de-force" call: which forced demo rules to DROP (the ">=5 tools", the
    canned prompts, the rigid one-file-per-thing) vs. which conventions are worth
    KEEPING for production — and why.
  - Which of the skill / subagent you keep, drop, or repurpose for the new agent.
  - The single build prompt you'll use to turn AGENT_SPEC.md into a running agent.
-->
