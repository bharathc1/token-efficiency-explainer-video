---
format: 1080x1080
duration: 60s
message: "Collate cut raw tokens per turn 68% and spend per turn 67% by changing how its agent harness moves context, with output unchanged"
arc: concept-explainer with process (one turn followed through the harness: result, then where it went, then three fixes, then back to the result)
audience: data and AI platform engineers running multi-agent systems
mode: autonomous
music: minimal calm tech underscore, low
---

## Video direction

- narrative thread: the video follows ONE turn through the harness. Question chain: "Same output, 68% fewer tokens: how?" (F1) -> "Each call re-sends context, so what did the spend go to?" (F2) -> "Mostly cache writes. Who reuses what?" (F3) -> Fix 1 order the prompt by who reuses it (F4) -> Fix 2 scope what each worker sees (F5) -> Fix 3 match recovery to the failure (F6) -> the three fixes add up to the hook's numbers (F7 callback). Every VO line ends on the hand-off to the next frame.
- thread rail: a persistent mono rail across the top 56px of every frame (built once as compositions/thread.html and mounted over all frames, NOT drawn by frame workers). Six stops: RESULT, CACHE, ORDER, SCOPE, RECOVER, TOTAL. The current stop is lit coral. Frame workers keep the top 64px of the canvas clear.
- callback: Frame 7 returns to the hook's exact numbers (2.306M to 0.739M) so the end closes the loop the start opened.

- palette system: `frame.md` code-editorial. Cream paper ground, ink type, one terracotta coral accent used only for the number or word that matters in a beat. Navy surface only for code-like panels (prompt blocks, token strips). Nothing invented outside `frame.md`.
- motion grammar: long-tail eases, `power3` default, smooth over bouncy. Every piece reveals on its spoken cue; at t=0 only what the VO is saying enters. During holds, stillness or a subtle jitter at most, no lazy breathing.
- rhythm: Frame 2 and Frame 7 are held, quiet frames (a comparison read and the closing questions). Frames 1, 3, 4, 5, 6 reveal on cues.
- shared visual stage: a horizontal "token strip" motif (rows of small blocks standing for tokens: uncached, cache write, cache read, output) recurs in Frames 1, 3, 4, 5 so the video reads as one continuing diagram.
- negative list: no stock imagery, no bokeh, no purple-blue AI gradients, no robot or brain icons, no logos. No slideshow (front-load then freeze) and no screensaver (everything floating independently).

## Frame 1 — Same output, far fewer tokens

- scene: Two huge numbers, 2.306M and 0.739M, with a coral minus-68% landing between them, a question hanging underneath
- voiceover: "Our agents write as much as before, but read sixty-eight percent fewer tokens. The savings came from how the harness moves context."
- duration: 8.673s
- transition_in: cut
- status: animated
- src: compositions/frames/01-hook.html
- type: hook
- persuasion: Counterintuitive claim + open question
- beat: surprise
- blueprint: dataviz-countup (Adapt)
- focal: the 2.306M to 0.739M raw-tokens-per-turn pair
- roles: 2.306M = foreground, ink, large · 0.739M = foreground, coral · -68% = emphasis · hairline grid = background, dim · label "raw tokens / turn" = supporting mono · closing line "how?" = supporting serif italic

Adapt: keep the count-up-to-one-hero-metric signature; the ring becomes the paired numbers counting down from 2.306M to 0.739M.
Scene 1 (0.0–4.0s): "Our agents write as much as before, but read sixty-eight percent fewer tokens." Kicker "RAW TOKENS PER TURN" at top; 2.306M enters large at center-left and counts down to 0.739M, recoloring coral as it lands; "-68%" pops beside it.
Scene 2 (4.0–10.0s): "The savings came from how the harness moves context." The pair settles and holds; a small serif-italic line "How?" fades in under the numbers on the final words, the open question the rest of the video answers.

narrativeRole: Opens the loop: a striking result with no explanation yet.
keyMessage: 68% fewer tokens per turn, with output unchanged, came from how context moves.

## Frame 2 — What a turn costs

- scene: One turn drawn as a short chain of model calls, each re-sending context; spend per turn drops from $3.66 to $1.22 with output flat
- voiceover: "A turn is many model calls, and each one re-sends context. Spend per turn fell from three sixty-six to one twenty-two."
- duration: 8.908s
- transition_in: crossfade
- status: animated
- src: compositions/frames/02-spend.html
- type: social_proof
- persuasion: Concretization + before/after
- beat: comprehension
- blueprint: comparison-split (Adapt)
- focal: two paired cards, "$3.66 per turn" and "$1.22 per turn", under a row of call chips
- roles: row of small call chips "call 1 · call 2 · call 3 · …" each with a context bar = supporting, ink · left card = foreground, tile surface · right card = foreground, coral number · output strip "OUTPUT / TURN 13.5K → 13.3K" = supporting, mono, under cards · background = cream

Adapt: keep the paired entry and the seam badge pop; stack top and bottom on the square canvas; badge reads "-67%". Add a call-chip row above the cards that explains why spend tracks context.
Scene 1 (0.0–5.0s): "A turn is many model calls, and each one re-sends context." A row of call chips builds left to right, each with a context bar of equal length riding along, one chip per spoken beat.
Scene 2 (5.0–10.0s): "Spend per turn fell from three sixty-six to one twenty-two." The chip row shifts up and dims; the $3.66 card enters from above, the $1.22 card from below, badge "-67%" pops on the seam, then the output strip slides in and holds still.

narrativeRole: Explains why token count turns into spend: every call re-sends context.
keyMessage: Spend tracks context moved, and it fell from $3.66 to $1.22 per turn.

## Frame 3 — Where the drop came from

- scene: A token strip shows cache writes shrinking from 864K to 179K while a 1.25x vs 0.1x price tag explains why, ending on a question
- voiceover: "Most of the drop was cache writes, down seventy-nine percent. A write only pays if something reads it again, so who reuses what?"
- duration: 9.404s
- transition_in: crossfade
- status: animated
- src: compositions/frames/03-cache-writes.html
- type: feature_showcase
- persuasion: Statistical proof + causal chain + question hand-off
- beat: comprehension
- blueprint: compose
- focal: a horizontal token strip whose cache-write segment shrinks
- roles: strip = foreground · cache-write segment = coral · cache-read segment = ink · "864K → 179K" and "-79%" = foreground labels · price tags "write 1.25x", "read 0.1x" = supporting mono · closing question "Who reuses what?" = serif italic, lands last · background = hairline grid

Scene 1 (0.0–4.0s): "Most of the drop was cache writes, down seventy-nine percent." The strip enters with a wide coral write segment labeled 864K, then the segment shrinks to 179K and "-79%" lands.
Scene 2 (4.0–7.0s): "A write only pays if something reads it again," The price tags rise under the strip: "write 1.25x", "read 0.1x" of an uncached input; an arrow loops from write to read.
Scene 3 (7.0–10.0s): "so who reuses what?" The strip dims and the serif-italic question "Who reuses what?" lands, the hand-off into Fix 1; hold still.

narrativeRole: Names the mechanism and poses the question the next three fixes answer.
keyMessage: Repeated cache writes were the waste; the fixes are about who reuses what.

## Frame 4 — Fix 1: order the prompt by who reuses it

- scene: Six planner call paths collapse onto one identical system prompt; the old 400K rewrite shrinks to zero
- voiceover: "One: order the prompt by who reuses it. Six planner paths now share an identical system prompt, so downstream agents read the router's cache with zero writes."
- duration: 11.154s
- transition_in: push-slide LEFT
- status: animated
- src: compositions/frames/04-prompt-order.html
- type: feature_showcase
- persuasion: Concretization + progressive disclosure
- beat: aha
- blueprint: compose
- focal: a stacked prompt block (shared prefix on top, role instructions at the bottom) fanned out to six call paths
- roles: shared system prompt block = foreground, navy surface · six small path chips = supporting · "390–410K history tokens rewritten per call" = coral label that wipes to "0 writes" · kicker "FIX 1" = mono · chip row echoes the call chips from Frame 2

Scene 1 (0.0–4.0s): "One: order the prompt by who reuses it." Kicker FIX 1; a navy prompt block builds top to bottom, shared context first, role instructions last, with the note "stable prefix first".
Scene 2 (4.0–8.0s): "Six planner paths now share an identical system prompt," Six small chips (routing, gate, remediation, synthesis…) fan out and each snaps onto the same block with an equals mark.
Scene 3 (8.0–12.0s): "so downstream agents read the router's cache with zero writes." The coral "390–410K tokens rewritten per call" label counts down and resolves to "0 writes"; hold still.

narrativeRole: First answer to "who reuses what": share one prefix across the calls that can reuse it.
keyMessage: Put content in a cached segment according to the calls that can reuse it.

## Frame 5 — Fix 2: scope what each worker sees

- scene: A 500K-character persona document narrows through a planner into small task cards for workers
- voiceover: "Two: scope what each worker sees. The planner reads the whole five-hundred-thousand-character persona document, then passes workers only the definitions they need."
- duration: 10.841s
- transition_in: push-slide LEFT
- status: animated
- src: compositions/frames/05-worker-context.html
- type: feature_showcase
- persuasion: Concretization + progressive disclosure
- beat: clarity
- blueprint: compose
- focal: one tall document block narrowing through a planner node into three small task cards
- roles: document block "AI Persona Context ~500K characters ≈ 125K tokens" = foreground, tile surface · planner node = coral accent · three worker task cards = foreground · kicker "FIX 2" = mono

Scene 1 (0.0–3.5s): "Two: scope what each worker sees." Kicker FIX 2; the tall document block enters, labeled "AI Persona Context, ~500K characters, ≈125K tokens".
Scene 2 (3.5–8.0s): "The planner reads the whole... persona document," The block feeds into a coral planner node on the right.
Scene 3 (8.0–12.0s): "then passes workers only the definitions they need." Three small cards peel off the planner, each holding a one-line "definition + identifier" snippet; hold still.

narrativeRole: Second answer: the planner owns the full context and hands each worker only its slice.
keyMessage: The planner copies relevant definitions into each worker's task instead of passing the whole document.

## Frame 6 — Fix 3: match recovery to the failure

- scene: A retry loop counting up to 44 model calls against a Query Runner marked unavailable, then the failure is classified and the loop stops
- voiceover: "Three: match recovery to the failure. One message burned forty-four calls retrying SQL while the Query Runner was down."
- duration: 8.986s
- transition_in: push-slide LEFT
- status: animated
- src: compositions/frames/06-recovery.html
- type: feature_showcase
- persuasion: Worked example + before/after
- beat: unease then relief
- blueprint: compose
- focal: a retry loop counter climbing to 44 beside a status chip "Query Runner: unavailable"
- roles: loop arrow and counter = foreground, coral · status chip = foreground, navy · "transport failure" vs "SQL failure" classifier labels = supporting mono · kicker "FIX 3" = mono · rule line "a recovery call should have a plausible way to change the outcome" = supporting serif italic, lands last

Scene 1 (0.0–3.0s): "Three: match recovery to the failure." Kicker FIX 3; a circular "regenerate SQL" arrow appears next to the chip "Query Runner: unavailable".
Scene 2 (3.0–7.0s): "One message burned forty-four calls retrying SQL" The counter spins up to 44 model calls with each loop.
Scene 3 (7.0–10.0s): "while the Query Runner was down." A classifier label snaps onto the chip, "transport failure, not a SQL failure", the loop arrow breaks off, and the serif-italic rule line fades in; hold still.

narrativeRole: Third answer: stop paying for retries that cannot change the outcome.
keyMessage: A recovery call should have a plausible way to change the outcome.

## Frame 7 — Back to the number

- scene: The three fixes recap as three lines, then the hook's numbers return as the payoff, then a quiet scope note
- voiceover: "Reuse the prefix, scope the context, fit the recovery. Output unchanged, sixty-eight percent fewer tokens. Make it observable."
- duration: 9.953s
- transition_in: crossfade
- status: animated
- src: compositions/frames/07-close.html
- type: cta
- persuasion: Rule of three + callback to the hook
- beat: resolve
- blueprint: kinetic-type-beats (Adapt)
- focal: the hook's pair "2.306M → 0.739M raw tokens / turn" returning large in coral below three recap lines
- roles: three recap lines "Reuse the prefix" "Scope the context" "Fit the recovery" = foreground serif, each tagged with its fix number in mono · "2.306M → 0.739M raw tokens / turn" = coral foreground, identical styling to Frame 1 · closer "Make token efficiency observable." = supporting serif italic · scope footnote = supporting small mono, "Collate's own agents · recorded provider charges only · not customer savings"

Adapt: keep the words-are-the-motion signature; each recap line lands as its own beat, then the callback numbers land.
Scene 1 (0.0–4.5s): "Reuse the prefix, scope the context, fit the recovery." Three recap lines land one per phrase, tagged 1, 2, 3.
Scene 2 (4.5–7.5s): "Output unchanged, sixty-eight percent fewer tokens." The recap dims and the numbers "2.306M → 0.739M raw tokens / turn" land large in coral, matching Frame 1 exactly.
Scene 3 (7.5–10.0s): "Make it observable." The closer line fades in; the scope footnote fades in small at the bottom; hold still.

narrativeRole: Closes the loop opened in Frame 1: the three fixes are how 2.306M became 0.739M.
keyMessage: Token efficiency is something you can observe, and these three moves produced the result.
