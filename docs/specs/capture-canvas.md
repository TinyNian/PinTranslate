# Capture canvas contracts

## Editing is non-destructive

When a user adds, changes, hides, or deletes an annotation or translation, the original Capture must remain unchanged and each edit must remain independently addressable until export. If an edit is flattened early, undo, restyling, and translation refresh can destroy prior work.

## Translation is an explicit network boundary

When OCR recognizes text, recognition and geometry must stay local; only the recognized text may be sent to the configured endpoint after the user invokes Translate. If pixels or text are uploaded implicitly, the app violates its local-first privacy boundary.

## Export renders visible layers in order

When a Canvas is copied or saved, export must render the Capture and every visible layer in display order at the Capture's native pixel scale. If export uses viewport coordinates or display scale, annotations drift or become blurry.

## Scrolling capture precedes editing

When a scrolling capture session is active, frames must be stitched into one immutable Capture before the Canvas is created. If annotations are allowed before stitching completes, their coordinates become invalid as the image height changes.

## Scrolling capture is user-driven and vertical

When a Scrolling capture starts, the selected screen region must remain fixed while the user manually scrolls its content vertically and the app captures overlapping frames. The app must not synthesize scroll events or incorporate horizontal movement; doing either makes behavior application-specific and can misalign the stitched Capture.
