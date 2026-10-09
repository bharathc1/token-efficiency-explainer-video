# Token Efficiency in Production: explainer video

A 1080x1080, ~68s narrated explainer of Collate's blog post "Token Efficiency in Production: Lessons From Running a Multi-Agent Platform". Built with [HyperFrames](https://hyperframes.heygen.com) (HTML to video), GSAP, and HeyGen text-to-speech.

## Pipeline

1. **Intake**: lock a brief (`BRIEF.md`): one message, concept angle, 1:1 for LinkedIn/X, ~60s.
2. **Source**: article text as the source of information (`capture/extracted/`).
3. **Design system**: `frame.md` from the open "code-editorial" preset (cream, ink, one coral accent). Fonts in `assets/fonts/` (EB Garamond, Inter, JetBrains Mono, all OFL).
4. **Story**: `STORYBOARD.md` + `SCRIPT.md`: 7 frames, one thread (result -> where it went -> 3 fixes -> back to the result), with a persistent top rail (`compositions/thread.html`).
5. **Audio**: narration with word timings and a music bed (HeyGen). Real narration length sets each frame's duration.
6. **Frames**: one HTML composition per frame in `compositions/frames/`, plus word-timed captions (`compositions/captions.html`).
7. **Assemble and check**: assemble `index.html`, inject transitions, then `npx hyperframes lint` and `check`, and review snapshots.
8. **Render**: `npx hyperframes render --quality high --output renders/video.mp4`.

## Rebuild

Generated audio is not committed. Sign in (`npx hyperframes auth login`), then regenerate narration from `SCRIPT.md` with your own HeyGen voice id, re-run caption/assemble, and render. If you change the voice, narration length changes: retime the frame timelines, rail (`STARTS` in `thread.html`) and captions.

## Notes

- All figures come from the source article; they measure Collate's own agents' recorded provider charges, not customer savings.
- Local fallback voice: Kokoro (`hyperframes tts`, needs `kokoro-onnx` in a venv).
