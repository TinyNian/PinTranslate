# Capture toolbar contracts

## The toolbar is the single capture control surface

When a screen selection is active, the Capture toolbar must contain the available annotation tools and capture actions: selection, freehand, straight line, rectangle or ellipse, arrow, text, undo, redo, Scrolling capture, Translate, Pin, Save, confirm, and cancel. A tool's style controls may expand contextually from its toolbar item, but must not require a detached editor window. Splitting these actions across unrelated surfaces makes the capture flow harder to learn and contradicts the toolbar's role.

## Toolbar controls expose real state

When a toolbar control is available, selected, processing, successful, failed, or keyboard-focused, its icon and control surface must communicate that state with more than color alone. If decorative motion or color replaces explicit state feedback, the visually rich toolbar becomes less usable than a conventional one.
