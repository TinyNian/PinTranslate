# PinTranslate

Pin screenshots above your workspace, annotate them, and translate recognized text in place with your own LLM.

PinTranslate is an open-source native macOS screenshot tool. The first usable release is centered on one flow: capture a region, edit it on a non-destructive canvas, pin it above other windows, and replace recognized text visually without changing the rest of the image.

## Planned capabilities

- Region screenshots
- Scrolling screenshots with automatic overlap stitching
- Lines, rectangles, arrows, and text annotations
- Custom stroke color, fill color, and opacity
- Always-on-top pinned screenshots
- On-device OCR with Apple Vision
- In-place translation through a user-supplied OpenAI-compatible endpoint

The interaction contract is still being sharpened before implementation. See [the domain map](docs/CONTEXT.md) for current terminology and boundaries.

## Principles

- Native macOS APIs before dependencies
- API keys stay in Keychain
- Captures and annotations stay local unless the user explicitly translates
- Editing remains non-destructive until export

## License

[MIT](LICENSE)
