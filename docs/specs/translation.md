# Translation contracts

## Translation is an explicit network boundary

When OCR recognizes text, recognition and geometry must stay local; only the recognized text may be sent to the configured endpoint after the user invokes Translate. If pixels or text are uploaded implicitly, the app violates its local-first privacy boundary.

## Translation preserves text-block position

When OCR groups recognized text into a paragraph block, its Translation layer must keep the block's original top-left anchor and width. It must fit the complete translation by wrapping first, then reducing the font size no lower than 9 pt at 100% view, then expanding downward if necessary. Truncating the translation violates the requirement to preserve its content at the source position.

## Colliding translation blocks reflow together

When a downward-expanded translation block would intersect the next translation block, the intersecting blocks must be merged and laid out again as one ordered group. Rendering independent overlapping blocks makes either translation unreadable.
