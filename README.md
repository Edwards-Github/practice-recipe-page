# What I Learned Building This Project

| Problem | Solution |
|---------|----------|
| **Incorrect use of heading tags**: I was using `<h3>` for "Preparation Time" just to make it look smaller visually | Heading tags describe document structure and importance, not size. Use CSS `font-size` to control appearance instead |
| **Nutrition section markup**: I originally used `<div>` pairs which made spacing hard to control | `<table>` is the semantically correct element for tabular data and already has built-in row/column behavior |
| **Nutrition table column spacing**: The values like "277kcal" weren't positioning correctly | Setting `width: 50%` on each `<td>` element splits the row evenly and combined with `justify-content: space-between` pushes values to opposite sides |
| **Repeated background colors**: Both `.preparation-title` and `.preparation` had the same `background-color` value | Wrapped both elements in a parent `<div>` and set the background color once on the parent instead (DRY principle) |
| **Verbose padding values**: Writing separate `padding-top`, `padding-right` etc. | Use padding shorthand: `padding: 10px 20px` where first value is top/bottom and second is left/right |
| **Text overflowing on mobile**: Fixed `width: 30%` caused content to overflow on narrow screens | Use `width: 100%` combined with `max-width: 700px` so the card flexibly fills the screen but never exceeds 700px. width: 100% with max-width: 700px doesn't actually set a minimum width. when the card is always 100% of the available width, the content inside never has to overflow because the card is always exactly as wide as the screen. There's no mismatch between the card size and the screen size. |
| **Different layouts for mobile vs desktop**: The card needed no border-radius, different padding, and a full-width image on mobile | Used `@media (max-width: 600px)` queries to apply mobile-specific styles only on smaller screens |
