## Bug Summary

- **Success Criterion:** 1.4.3
- **Standard:** AA
- **Severity:** 1

<!-- description -->

Text or UI components have insufficient color contrast ratio against their background, making content difficult to perceive for users with low vision or color vision deficiencies.

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

<!-- Textual description of fix -->

Ensure all text and interactive elements meet minimum contrast requirements:

- **Normal text (less than 18pt or 14pt bold):** minimum 4.5:1 contrast ratio
- **Large text (at least 18pt or 14pt bold):** minimum 3:1 contrast ratio
- **UI components and graphical objects:** minimum 3:1 contrast ratio

Use color contrast analyzers to verify ratios. Consider using darker text on light backgrounds or lighter text on dark backgrounds. Avoid using color as the only means of conveying information.

### Example

html

```html
<!-- Poor contrast -->
<p style="color: #999999; background-color: #FFFFFF;">Our cat adoption process is simple.</p>

<!-- Good contrast (4.6:1) -->
<p style="color: #767676; background-color: #FFFFFF;">Our cat adoption process is simple.</p>

<!-- Poor contrast button -->
<button style="color: #FFFFFF; background-color: #7AB0D7;">Adopt a cat</button>

<!-- Good contrast button (4.7:1) -->
<button style="color: #FFFFFF; background-color: #3E7FB3;">Adopt a cat</button>

<!-- Large text with acceptable contrast for large text (3.2:1) -->
<h1 style="font-size: 24px; color: #707070; background-color: #FFFFFF;">Cat of the Month</h1>
```

---

## Notes

<!-- Notes, if any -->

---

## Resources

- [WCAG 2.1 Success Criterion 1.4.3: Contrast (Minimum)](https://www.w3.org/WAI/WCAG21/Understanding/contrast-minimum.html)
- [Technique G18: Ensuring that a contrast ratio of at least 4.5:1 exists between text and background](https://www.w3.org/WAI/WCAG21/Techniques/general/G18)
- [Technique G145: Ensuring that a contrast ratio of at least 3:1 exists between text and background behind the text](https://www.w3.org/WAI/WCAG21/Techniques/general/G145)
- [Technique G174: Providing a control with a sufficient contrast ratio that allows users to switch to a presentation that uses sufficient contrast](https://www.w3.org/WAI/WCAG21/Techniques/general/G174)
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
