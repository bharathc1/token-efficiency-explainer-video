---
workflow: faceless-explainer
flow: automation
storyboard: no
message: "Collate cut tokens per turn 68% and spend per turn 67% by changing how its harness moves context, not by cutting output"
destination: linkedin-x-feed
aspect: 1080x1080
language: en
length: 60s
angle: concept
---

## Intent

Short explainer of Collate's blog "Token Efficiency in Production: Lessons From Running a Multi-Agent Platform". Lead with the result (2.306M to 0.739M raw tokens per turn; $3.66 to $1.22 per turn; output flat at about 13K), then show the mechanisms: cache reuse, prompt sharing scope, worker context, recovery that matches the failure. Engineering audience (data/AI platform teams). Confident, precise, no hype.

## Notes

- Use only numbers from the source doc. Do not call Collate "a catalog".
- Scope caveat to keep: figures are Collate's own agents' running cost, recorded provider charge only, not customer savings.
- Open source tooling: HyperFrames + local Kokoro TTS (HeyGen sign-in expired; offline engines).
