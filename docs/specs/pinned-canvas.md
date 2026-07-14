# Pinned canvas contracts

## A pinned canvas opens in viewing mode

When the user activates Pin from the capture toolbar, the capture interface must close and the Canvas must open in a movable always-on-top window in viewing mode. Dragging the visible image moves the window; if drawing tools remain active by default, window movement and annotation gestures conflict.

## Editing is an explicit mode

When the pointer enters a Pinned canvas, its controls must reveal Translate, Edit, Copy, Save, and Close. Activating Edit enters annotation mode; leaving or completing Edit returns to viewing mode. If annotation begins without that explicit transition, an ordinary drag can alter the Canvas instead of moving it.
