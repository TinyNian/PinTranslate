# Use native macOS frameworks with a layered canvas

PinTranslate will use Swift with AppKit, Core Graphics, ScreenCaptureKit, Vision, and Keychain rather than Electron/Tauri or a third-party image editor. This keeps capture permissions, window levels, native pixel coordinates, OCR, and secret storage inside platform APIs, while one non-destructive layered Canvas model serves annotations, translation overlays, pinning, and export. The trade-off is a macOS-only codebase and more custom canvas interaction code.
