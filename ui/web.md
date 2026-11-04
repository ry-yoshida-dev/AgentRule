# Web UI Rules

## Controls

- Give buttons icons so that they are intuitive. Icon-only buttons must have a tooltip and an `aria-label`.
- Draw custom icons with only the marks needed to convey the meaning. Leave out decorative or contextual strokes, such as ground lines or frames, that add nothing to it.
- Use a slider (`<input type="range">`) for parameters with a known range, and show the current value next to it.
- Show unavailable controls in a disabled state instead of hiding them.

## Keyboard

- Do not remove the visible focus indicator.
- Sliders and other value controls must respond to the arrow keys.

## Layout

- Keep layouts usable down to narrow windows without horizontal page scrolling.
- Keep the layout and control positions stable when settings or state change.
- Apply progressive disclosure by separating complex content into screens or steps, not by revealing controls in place.

## Desktop Browsers

Apply this section when desktop browsers are a primary target.

- Design for desktop browsers first, and make dense panes and tables usable through resizing, sorting, and filtering.
- Add shortcuts for frequent actions, and show them in the tooltip.
- Support drag and drop where files are accepted.

## States

- Every view that loads data must handle loading, empty, and error states.
- Long-running operations must show progress and be cancellable.
- Show the server connection state when the UI depends on a live backend connection, and contain render failures so that they do not take down the whole page.

## Verification

- After any screen change, run the build and open the changed screen in a browser. Report honestly when it could not be verified visually.
