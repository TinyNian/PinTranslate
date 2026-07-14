# Annotation contracts

## Straight lines and freehand paths are different tools

When the user selects the straight-line tool, dragging must create one segment between the drag endpoints. When the user selects the freehand tool, dragging must record a continuous pointer path. Both annotations must retain editable stroke color, thickness, and opacity; treating them as one tool would make either precise line placement or natural drawing unreliable.
