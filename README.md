# Calibrated Reasoning Prompt System

A composable system prompt framework for getting more epistemically honest, uncertainty-aware responses from large language models.

## The Problem

LLMs are trained to sound confident and helpful. This is commercially optimal and epistemically dangerous. The most harmful failure mode isn't obvious wrongness — it's **confident + fluent + wrong**, where the model's output feels authoritative precisely when it shouldn't be trusted.

This framework attempts to correct for that at the prompt level.

## Structure

```
base_prompt.md          — Universal epistemic rules, applies everywhere
overlay_health.md       — Additional rules for medical topics
overlay_legal.md        — Additional rules for legal topics  
overlay_financial.md    — Additional rules for financial topics
overlay_mental_health.md — Additional rules for mental health topics
```

## How to Use

**For general use:** Use `base_prompt.md` alone as your system prompt.

**For domain-specific use:** Combine the base prompt with the relevant overlay. Paste both into your system prompt, base first.

**For multi-domain conversations:** Stack multiple overlays. The base rules apply everywhere; overlays add domain-specific red flags and escalation triggers.

## What This Does

- Forces inline uncertainty markers (⚠️ 🔴 ✅) at the claim level rather than vague end disclaimers
- Explicitly categorizes what LLMs are and aren't reliable for
- Installs a correction protocol that extracts lessons from errors
- Adds domain-specific red flags where hallucination risk is highest
- Defines escalation triggers for decisions that exceed what AI should weigh alone

## What This Doesn't Do

- Fix the underlying model. Hallucination is still possible — this makes it more visible, not impossible.
- Help someone in acute mental health crisis who is seeking confirmation of distorted beliefs. That requires human intervention.
- Replace domain expertise. The overlays are not a substitute for professionals — they help you use AI *alongside* professionals more safely.

## Limitations

This works best for users who already have enough domain knowledge to recognize when something seems off. It improves calibration for skeptical users. It provides less protection for users who are highly trusting of AI output by default — which is, unfortunately, most users.

That's a product and policy problem, not something a prompt can fully solve.

## Contributing

If you improve these prompts, share the changes. The goal is a public commons of better epistemics, not a personal tool.

---

*Born from a conversation about why "I don't know" is the most underrated thing an AI can say.*
