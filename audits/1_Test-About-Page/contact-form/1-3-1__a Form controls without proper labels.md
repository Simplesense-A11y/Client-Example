## Bug Summary

- **Success Criterion:** 1.3.1 Info and Relationships
- **Standard:** AA
- **Severity:** 1

Form controls without programmatically associated labels prevent screen reader users from understanding the purpose of form fields, making forms difficult or impossible to complete independently.

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

Form controls must be programmatically associated with their visual labels to ensure screen reader users can understand their purpose. There are multiple ways to create this association:

1. Use the `<label>` element with the `for` attribute that matches the form control's `id`
2. Wrap the form control inside a `<label>` element
3. Use `aria-labelledby` pointing to the ID of the text that serves as the label
4. Use `aria-label` when there is no visible text label but a label is still needed

If a form control is already labeled by another method, don't add additional labeling methods as this can cause screen readers to announce the label twice.

### Example

html

```html
<!-- Method 1: Using label with for attribute -->
<label for="cat-name">Cat's Name</label>
<input type="text" id="cat-name" name="cat-name">

<!-- Method 2: Wrapping input in label -->
<label>
  Cat's Age
  <input type="number" name="cat-age">
</label>

<!-- Method 3: Using aria-labelledby -->
<p id="cat-color-label">Cat's Color</p>
<select aria-labelledby="cat-color-label" name="cat-color">
  <option value="black">Black</option>
  <option value="white">White</option>
  <option value="orange">Orange</option>
</select>

<!-- Method 4: Using aria-label (when no visible label) -->
<input type="search" aria-label="Search for cat breeds" name="cat-search">

<!-- Avoid: Form control without proper label -->
<p>Cat's Weight</p>
<input type="text" name="cat-weight"> <!-- No programmatic association! -->
```

---

## Resources

- [H44: Using label elements to associate text labels with form controls](https://www.w3.org/WAI/WCAG21/Techniques/html/H44)
- [ARIA16: Using aria-labelledby to provide a name for user interface controls](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA16)
- [Understanding Success Criterion 1.3.1: Info and Relationships](https://www.w3.org/WAI/WCAG21/Understanding/info-and-relationships.html)
