# Week 2 Project — Scope, Plan & MVP

**Project:** Essence (personal summarizer assistant): a single-task AI assistant that condenses any pasted text into a consistent four-part structure.
**Tagline:** "The meaning matters. Every detail counts."
**Failure mode:** adding or dropping details that change the meaning.
**Timeline:** Scope Day 3 (today) → Build Day 4 → Demo Day 5

---

## Scope

**In scope (one task):** summarize text the user pastes in, using the fixed structure: Summary, Key Points, Key Facts to Verify, Not Stated.

**Out of scope (scope-creep guardrails):**
- Answering questions about the text
- Rewriting, editing or translating it
- Summarizing from links or file uploads (paste only)
- Changing summary length or style (no "short / long" modes)
- Web lookups or adding outside context
- A custom UI or app (tech stays light)

If an idea comes up during the build that falls outside this list, log it under "Future ideas" in the Prompt Log instead of building it.

---

## MVP (the minimum that meets the spec)

| Spec requirement | MVP version | Status |
|---|---|---|
| System prompt (role + rules) | In README | ✅ Drafted |
| 1–2 few-shot examples | Library announcement and workplace email | ✅ Drafted |
| Consistent output structure | Four fixed sections | ✅ Drafted |
| Responsible-use note | Safe data, hallucination and bias risks, how to verify, when not to use | ✅ Drafted |
| Reliability test (3+ inputs) | 5 tests, including failure-mode and injection tests | ⬜ Run on Day 4 |
| Named failure mode + mitigation | Adding or dropping meaning-changing details, with 4 mitigations | ✅ Drafted, ⬜ prove with Test #4 |
| Design choices in own words | Section in README | ⬜ Reword in own voice |
| Prompt Log of iterations | Week 2 Prompt Log | ⬜ Log each Day 4 iteration |
| The assistant (link or doc) | Custom GPT link, with the README as documented backup | ⬜ Build GPT |
| One-page spec sheet | Separate 1-page doc | ⬜ Create |

**Build format:** a **Custom GPT** in the Next Chapter workspace (see `custom-gpt-build-kit.md`), created before OpenAI ends new GPT creation on Sept 25, 2026. The README stays the documented backup. Fallback: a Claude Project with the same instructions.

---

## Day-by-Day Plan

### Day 3 (today): Scope ✅
- [x] Choose the task and failure mode
- [x] Draft the system prompt, examples, structure and responsible-use note (README)
- [x] Plan the reliability tests
- [ ] Gather test inputs: a news article, a Next Chapter reading excerpt, a casual message (#4 and #5 are already written)

### Day 4: Build and test
1. **Baseline run (for the log):** paste Test #4 into a plain chat with no system prompt, just "summarize this." Save the result. This shows what goes wrong without the build.
2. **Run all 5 tests** in fresh chats with the system prompt and examples. Screenshot each one.
3. **Score each test:** structure followed? Numbers and limiting words kept? Anything added? Injection ignored?
4. **Iterate:** if a test fails, change one thing in the prompt, re-run it and log what changed and why. Aim for 2–3 logged iterations.
5. **Fill in the Results column** in the README.
6. **Reword the Design Choices section** in your own words.
7. **Write the one-page spec sheet.**
8. Build the Custom GPT first, before running the tests, using the build kit.

### Day 5: Demo
1. **Live run:** summarize one fresh input and point out the four sections.
2. **Show the failure:** the baseline (no system prompt) version of Test #4 dropping "only" or "up to," then your assistant keeping them. Walk through how Key Facts to Verify catches it.
3. **Close with the responsible-use note:** what's safe to paste and how to verify.
4. **Backup:** have screenshots ready in case the live run misbehaves. If it does, that's a real failure mode to talk about.

---

## Deliverables Checklist
- [ ] The assistant: README (and GPT link if built)
- [ ] One-page spec sheet
- [ ] Prompt Log with Day 4 iterations
- [ ] Test screenshots (demo backup and evidence)

## Rubric Map
- **Build skill:** 5 tests pass consistently
- **Control:** tight scope list, design choices in own words, logged iterations, named failure mode
- **Demo:** live run, plus the baseline-vs-assistant failure comparison
- **Meets the spec:** every row in the MVP table checked
