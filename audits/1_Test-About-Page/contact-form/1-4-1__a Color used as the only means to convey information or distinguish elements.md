## Bug Summary

- **Success Criterion:** 1.4.1 Use of Color
- **Standard:** A
- **Severity:** 1

Color is being used as the only visual means of conveying information, indicating an action, prompting a response, or distinguishing a visual element.

---

## Details

### Element Description

<!-- Textual description of affected element's or component's location, state, etc. and screenshots-->

All input fields when in error

### Element Selector

<!-- CSS or JS selector -->

`#fname`

### Steps to Reproduce

<!-- Steps required to reproduce the bug -->

Submit the form with empty input values

---

## Solution

### Solution Summary

Information conveyed through color must also be available through other visual means that don't rely on color perception. This ensures users with color blindness, low vision, or those using monochrome displays can access the same information.

For each case where color alone is being used to convey information, implement at least one alternative method:

1. **For links:** Add underlines, bold text, or icons
2. **For form elements:** Include visible labels, borders, or icons
3. **For status indicators:** Add text labels, icons, or patterns
4. **For charts/graphs:** Use patterns, shapes, labels, or textures in addition to color
5. **For distinguishing between elements:** Add text labels, icons, borders, or patterns

### Example

html

```html
<!-- BAD: Link using only color difference -->
<p>Please see our <a href="/policy" style="color: blue;">privacy policy</a> for more information.</p>

<!-- GOOD: Link with underline -->
<p>Please see our <a href="/policy" style="text-decoration: underline;">privacy policy</a> for more information.</p>

<!-- BAD: Error state indicated only by red outline -->
<input type="text" class="error-field" style="border: 2px solid red;">

<!-- GOOD: Error state with icon and text -->
<div>
  <input type="text" aria-describedby="error-message">
  <span id="error-message" class="error">
    <img src="cat-error-icon.svg" alt=""> Email is required
  </span>
</div>

<!-- BAD: Chart using only color to distinguish data series -->
<div class="chart">
  <!-- Chart with cat adoption rates shown only by color differences -->
</div>

<!-- GOOD: Chart using patterns and labels -->
<div class="chart">
  <!-- Chart with cat adoption rates shown with patterns, shapes and colors -->
  <div class="legend">
    <div><span class="stripe-pattern"></span> Tabby cats</div>
    <div><span class="dot-pattern"></span> Black cats</div>
  </div>
</div>
```

---

## Notes

<!-- Notes, if any -->

This applies to all input fields on the page 

---

## Resources

- [G183: Using a contrast ratio of 3:1 with surrounding text and providing additional visual cues on hover](https://www.w3.org/WAI/WCAG21/Techniques/general/G183)
- [F73: Failure due to creating links that are not visually evident without color vision](https://www.w3.org/WAI/WCAG21/Techniques/failures/F73)
- [G14: Ensuring that information conveyed by color differences is also available in text](https://www.w3.org/WAI/WCAG21/Techniques/general/G14)
- [G111: Using color and pattern together](https://www.w3.org/WAI/WCAG21/Techniques/general/G111)
- [G182: Ensuring that additional visual cues are available when text color differences are used to convey information](https://www.w3.org/WAI/WCAG21/Techniques/general/G182)
- [G175: Providing a multi color selection tool on the page for foreground and background colors](https://www.w3.org/WAI/WCAG21/Techniques/general/G175)
- [Understanding Success Criterion 1.4.1: Use of Color](https://www.w3.org/WAI/WCAG21/Understanding/use-of-color.html)
