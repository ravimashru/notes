# Margin Collapsing

- Margins of blocks are combined (collapsed) into single margin whose size is largest of individual margins. (Blocks = block elements. Margin collapsing doesn't happen if there is a different `display` property, e.g. `display: flex;`)

- Affects only top and bottom margins.

- Does not affect margins of floating and absolutely positioned elements.



## Cases when margin collapsing occurs:

1. Margins of adjacent siblings are collapsed (exception: lower sibling needs to be cleared past floats).
2. If there is no content separating the `margin-top` of a parent from that of one of its decendants, collapsed margin ends up outside the parent. The same goes for `margin-bottom`.
3. If there is no content in a block to separate its `margin-top` from its `margin-bottom` then the top and bottom margins collapse.



- More complex margin collapsing can occur when above cases are combined.
- The rules apply even to zero margin.
- When negative margins are used, collapsed margin = largest positive margin + most negative margin.
- When all margins are negative, collapsed margin is the most negative margin.




**Source:** https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Box_Model/Mastering_margin_collapsing
