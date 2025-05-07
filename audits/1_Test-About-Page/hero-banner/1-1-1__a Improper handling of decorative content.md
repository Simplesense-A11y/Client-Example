## Bug Summary

- **Success Criterion:** 1.1.1 Non-text Content
- **Standard:** A
- **Severity:** 1

Decorative elements are not properly hidden from assistive technology, causing unnecessary noise and confusion for screen reader users. Alternatively, elements that should be treated as decorative are being exposed to screen readers with unhelpful or redundant information.

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

Decorative elements that don't convey meaningful information should be hidden from screen reader users to reduce noise and improve the user experience. There are several techniques to properly hide decorative content:

1. **For images:** Use an empty `alt` attribute (`alt=""`), not `alt="null"` or `alt="decorative"`
2. For SVG images: Use `aria-hidden="true"`
3. For icon fonts or purely decorative elements: Use `aria-hidden="true"` or `role="presentation"` or `role="none"`
4. For CSS background images: No additional markup is needed as they are already hidden from screen readers

Conversely, ensure that elements with informational value are NOT marked as decorative.

### Example

html

```html
<!-- CORRECT: Empty alt attribute for decorative image -->
<img src="cat-pattern-background.png" alt="">

<!-- CORRECT: Using aria-hidden for decorative SVG -->
<svg aria-hidden="true">
  <path d="M10,10 C30,30 30,10 50,10" fill="none" stroke="#000" />
</svg>

<!-- CORRECT: Using role="presentation" for decorative icon -->
<i class="icon cat-paw-icon" role="presentation"></i>

<!-- INCORRECT: Decorative image with unhelpful alt text -->
<img src="cat-pattern-background.png" alt="background image">
<img src="cat-pattern-background.png" alt="decorative">
<img src="cat-pattern-background.png" alt="cat pattern">

<!-- INCORRECT: Informative image incorrectly marked as decorative -->
<img src="cat-adoption-chart.png" alt="" aria-hidden="true">
```

---

## Notes

<!-- Notes, if any -->

---

## Resources

- [WCAG 1.1.1: Non-text Content](https://www.w3.org/WAI/WCAG21/Understanding/non-text-content.html)
- [H67: Using null alt text and no title attribute on img elements for images that AT should ignore](https://www.w3.org/WAI/WCAG21/Techniques/html/H67.html)
- [ARIA10: Using aria-hidden="true" on content that is visually hidden](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA10.html)
- [WebAIM: Alternative Text](https://webaim.org/techniques/alttext/)
