## Bug Summary

- **Success Criterion:** 2.2.2 Pause, Stop, Hide
- **Standard:** A
- **Severity:** 1

Moving, blinking, scrolling, or auto-updating content must have controls that allow users to pause, stop, or hide the content.

---

## Details

### Element Description

<!-- Textual description of affected element's or component's location, state, etc. and screenshots-->

### Element Selector

<!-- CSS or JS selector -->

### Steps to Reproduce

<!-- Steps required to reproduce the bug -->

---

## Solution

### Solution Summary

Content that automatically moves, blinks, scrolls, or updates for more than 5 seconds needs a mechanism for users to pause, stop, or hide it. This is essential for:

- **Cognitive accessibility:** Moving content can be distracting for users with attention disorders
- **Physical accessibility:** Auto-updating content may not give sufficient time for users with motor impairments to read or interact
- **Visual accessibility:** Blinking content can trigger seizures or discomfort in users with photosensitive conditions

Implement one or more of these solutions:

1. Add controls to pause, stop, or hide the moving content
2. Set a time limit for the animation (if under 5 seconds, no controls needed)
3. Allow users to disable animations site-wide through preferences

### Example

**Carousel with pause button:**

- Create a cat image carousel with an accessible pause button
- Include a button with `aria-pressed` attribute to indicate state
- Provide a clear visual label and icon for the button
- Use `aria-live="polite"` on the carousel container for screen reader announcements

**Auto-updating content with controls:**

- For content that refreshes automatically (like a feed of cat status updates)
- Add a toggle button with clear labeling like "Pause Updates"
- Implement `aria-live="polite"` on the updating region
- Ensure the pause state persists until user chooses to resume

**Animation controls with respect for user preferences:**

- Honor the `prefers-reduced-motion` media query to disable animations
- Use CSS `animation-play-state: paused` when controls are activated
- Provide a clearly labeled button to toggle animation states
- Ensure animation controls are keyboard accessible

**Important:** All controls must be:

- Keyboard accessible
- Clearly labeled (visually and for assistive technology)
- Properly implement ARIA states (`aria-pressed`, etc.)
- Visible and operable by all users

---

## Notes

<!-- Notes, if any -->

---

## Resources
