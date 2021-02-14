# `DocumentFragment`

- Lightweight version of `Document`.
- Not part of active document tree structure (has no parent in active document).
- Stores nodes like standard document, but changes made in fragment don't affect active document (no performance impact when changes made to fragment), even on reflow.

## Common Usage

- Create a `DocumentFragment` and assemble DOM subtree in it.
- Append fragment to active document using methods like `appendChild()` or `insertBefore()`.
- All nodes in fragment inserted into the document only once, therefore only one reflow and render is required.
- Moving fragment's nodes into active document leaves behind empty fragment.

## References
- https://developer.mozilla.org/en-US/docs/Web/API/DocumentFragment
