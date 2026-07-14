# Capture toolbar contracts

## The toolbar is the single capture control surface

When a screen selection is active, the Capture toolbar must contain the available annotation tools and capture actions: selection, freehand, straight line, rectangle or ellipse, arrow, text, undo, redo, Scrolling capture, Translate, Pin, Save, confirm, and cancel. A tool's style controls may expand contextually from its toolbar item, but must not require a detached editor window. Splitting these actions across unrelated surfaces makes the capture flow harder to learn and contradicts the toolbar's role.

## Toolbar controls expose real state

When a toolbar control is available, selected, processing, successful, failed, or keyboard-focused, its icon and control surface must communicate that state with more than color alone. If decorative motion or color replaces explicit state feedback, the visually rich toolbar becomes less usable than a conventional one.

## The first release uses a vertical capsule

When the Capture toolbar appears, it must use one light vertical capsule with a single column of icon controls. The selected tool must use a dark circular field with an inverted icon, and hover or keyboard focus must reveal the tool name in a small capsule beside that icon. This reference layout is the first-release baseline; a distinctive high-fidelity visual system is deliberately deferred until the capture workflow is proven.

## Tool properties remain attached to the active icon

When an annotation tool is active, its color, thickness, fill, opacity, and text controls must open in a secondary capsule beside the active icon. The property capsule must light-dismiss without changing tools. Moving these controls into a settings window breaks the direct relationship shown by the toolbar reference.

## The toolbar stays inside the active screen

When the selection leaves insufficient room on the toolbar's preferred side, the toolbar and any property capsule must flip to another side while staying fully inside the current screen. If the screen is too short for every control, the icon column may scroll while confirm and cancel remain fixed and visible. Clipping actions outside the screen makes the single-surface contract unusable.
