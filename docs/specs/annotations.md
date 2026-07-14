# Annotation contracts

## Straight lines and freehand paths are different tools

When the user selects the straight-line tool, dragging must create one segment between the drag endpoints. When the user selects the freehand tool, dragging must record a continuous pointer path. Both annotations must retain editable stroke color, thickness, and opacity; treating them as one tool would make either precise line placement or natural drawing unreliable.

## Shape annotations include rectangles and ellipses

When the user selects a shape tool, they must be able to choose a rectangle or ellipse and drag its bounds on the Canvas. Both shapes must use the same editable stroke and fill style model; implementing separate behavior for each would create inconsistent controls without adding capability.
