# Annotation contracts

## Straight lines and freehand paths are different tools

When the user selects the straight-line tool, dragging must create one segment between the drag endpoints. When the user selects the freehand tool, dragging must record a continuous pointer path. Both annotations must retain editable stroke color, thickness, and opacity; treating them as one tool would make either precise line placement or natural drawing unreliable.

## Shape annotations include rectangles and ellipses

When the user selects a shape tool, they must be able to choose a rectangle or ellipse and drag its bounds on the Canvas. Both shapes must use the same editable stroke and fill style model; implementing separate behavior for each would create inconsistent controls without adding capability.

## Shape stroke and fill styles are independent

When a rectangle or ellipse is selected, its stroke must retain editable color, thickness, and opacity while its fill can be disabled or retain a separate color and opacity. Changing fill opacity must not change stroke opacity; coupling them prevents a translucent highlight from keeping a clear boundary.

## Text annotations separate text and background styles

When the user creates a text annotation, it must use the macOS system font and retain editable text color, text opacity, font size, and regular or bold weight. Its resizable text box must wrap automatically and may have no background or a background with independent color and opacity. Coupling text and background opacity prevents a translucent highlight from keeping readable text.
