# Translation contracts

## Translation is an explicit network boundary

When OCR recognizes text, recognition and geometry must stay local; only the recognized text may be sent to the configured endpoint after the user invokes Translate. If pixels or text are uploaded implicitly, the app violates its local-first privacy boundary.

## Translation preserves text-block position

When OCR groups recognized text into a paragraph block, its Translation layer must keep the block's original top-left anchor and width. It must fit the complete translation by wrapping first, then reducing the font size no lower than 9 pt at 100% view, then expanding downward if necessary. Truncating the translation violates the requirement to preserve its content at the source position.

## Colliding translation blocks reflow together

When a downward-expanded translation block would intersect the next translation block, the intersecting blocks must be merged and laid out again as one ordered group. Rendering independent overlapping blocks makes either translation unreadable.

## Translation masks adapt to the source background

When a Translation layer covers source text on a low-variance background, it must sample nearby pixels and fill the text block with a matching opaque color before drawing the translation. When the background is textured or image-like, it must use a high-opacity lightly blurred mask instead. Attempting seamless reconstruction would either produce unreliable artifacts or require sending captured pixels across the network, while leaving the source text visible makes both languages unreadable.

## The first provider boundary is OpenAI-compatible

When the user configures translation, the first release must accept an OpenAI-compatible Chat Completions Base URL, model name, optional API key, and target language. The API key must be stored in macOS Keychain and must never appear in preferences files or logs. Adding native protocols for individual model providers before a real compatibility requirement exists would create speculative adapters and a wider secret-handling surface.
