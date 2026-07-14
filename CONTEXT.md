# PinTranslate Domain Map

PinTranslate owns the local workflow from screen capture to non-destructive composition, pinned presentation, and optional LLM translation. It does not own remote storage, accounts, or translation-provider data.

## Read Next

| Area | Current contract | Decisions |
| --- | --- | --- |
| Capture and composition | [Capture canvas](docs/specs/capture-canvas.md) | [Native macOS architecture](docs/adr/0001-native-macos.md) |
| Pinned presentation | [Pinned canvas](docs/specs/pinned-canvas.md) | [Native macOS architecture](docs/adr/0001-native-macos.md) |

## System Relationships

`Screen region → Capture → Canvas → Annotation / Translation layers → Pin or Export`

A scrolling capture produces one Capture before it enters the same Canvas flow as a region capture.

## Global Invariants

- Editing never mutates the original capture; annotations and translations are separate layers until export. Details: [capture canvas](docs/specs/capture-canvas.md).
- Captured pixels stay on the Mac unless the user explicitly invokes translation. Details: [capture canvas](docs/specs/capture-canvas.md).
- A Pinned canvas separates window movement from annotation gestures. Details: [pinned canvas](docs/specs/pinned-canvas.md).

## Language

**Capture**: The immutable pixel image produced by a region or scrolling capture. _Avoid_: Screenshot file

**Region capture**: A Capture produced from one fixed rectangular screen selection without scrolling. _Avoid_: Normal screenshot

**Canvas**: A Capture plus ordered editable layers and viewport state. _Avoid_: Image

**Annotation layer**: User-created lines, rectangles, arrows, or text with independent style properties. _Avoid_: Markup baked into the screenshot

**Translation layer**: OCR regions paired with translated text and layout metadata. _Avoid_: Translated screenshot

**Pinned canvas**: A Canvas presented in a movable always-on-top window. _Avoid_: Floating screenshot

**Scrolling capture**: A Capture assembled from overlapping frames of one fixed screen region while the user manually scrolls its content vertically in one direction. _Avoid_: Full-page capture, automatic scrolling capture
