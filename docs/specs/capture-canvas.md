# Capture canvas contracts

## A region selection has conventional completion controls

When the user releases a completed rectangular selection for a Region capture, an action toolbar with confirm and cancel controls must appear next to the selection. Double-clicking inside the selection or activating the checkmark confirms it; activating the cross cancels it. If completion is only available through a detached window or an undiscoverable shortcut, the capture flow no longer behaves like a conventional screenshot tool.

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

## A scrolling session has one direction

When the first valid frame extension establishes a Scrolling capture's direction, every later frame must extend that same direction until completion. The default instruction is to scroll downward; if reverse movement is detected, capture must pause, exclude those frames, and tell the user to continue in the established direction. Accepting reverse frames can duplicate or reorder content in the stitched Capture.

## Scrolling capture completes from the toolbar

When a Scrolling capture is recording, the selection must pass pointer and scroll input through to the source application while its action toolbar remains interactive. Only the toolbar checkmark completes the stitched Capture and only the toolbar cross cancels it; double-clicking inside the selected region must not complete the capture. Intercepting that double-click can block or accidentally activate content in the source application.
