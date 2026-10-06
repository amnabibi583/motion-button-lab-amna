# Motion Button Lab

Standalone interactive button demo using only `index.html`, embedded CSS, and embedded JavaScript.

## States and testing

- **Send message:** idle blue state with send icon; hover/focus lifts and scales; click shows a loading state with a spinner and fake 650–1450ms request.
- **Success:** 80% random chance, or use **Force success**. The button turns green, shows `✓ Sent` for 1.2 seconds, then resets.
- **Error:** 20% random chance, or use **Force error**. The button turns red, shows `Retry`, shakes once for 360ms, then resets after 1.8 seconds.
- **Save draft:** click to see `Saving…`, then `✓ Draft saved`, then the idle label returns.
- **Random result / Force success / Force error:** choose the result used by the next send request.

## Accessibility and motion

The controls are native keyboard-accessible buttons with visible focus outlines and a live status region for screen readers. Buttons are disabled while their fake operation runs, so extra clicks are ignored. Motion uses transform and opacity for content transitions; the only layout property animated is the small button-width change during loading. Hover/focus uses 180ms, loading width uses 220ms, success remains for 1.2 seconds, and the error shake runs once for 360ms. `prefers-reduced-motion: reduce` removes transitions, spinner animation, and shaking while preserving labels, colors, and feedback.
