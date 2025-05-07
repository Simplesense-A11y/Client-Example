## Bug Summary

- **Success Criterion:** 3.3.3
- **Standard:** AA
- **Severity:** 1

<!-- description -->

Error messages identify input errors but don't provide suggestions for correction when such suggestions are known and can be provided without compromising security or purpose.

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

When form validation errors occur, provide clear and specific suggestions for correcting the error whenever possible. Error messages should not only identify what went wrong but also explain how to fix it. This helps all users, particularly those with cognitive disabilities, to successfully complete forms.

**Error message recommendations:**

- **Be specific:** Clearly identify what's wrong and how to fix it
- **Be constructive:** Offer actionable guidance rather than just stating the problem
- **Be contextual:** Place error messages near the relevant field
- **Be accessible:** Ensure error messages are announced to screen reader users

**Implementation methods:**

- Use `aria-describedby` to associate error messages with their form fields
- Implement proper form validation with descriptive error text
- Consider adding examples of correct input format
- Use appropriate ARIA attributes to programmatically indicate errors

### Example

html

```html
<!-- Poor example (only identifies error) -->
<label for="cat-age">Cat's Age:</label>
<input type="text" id="cat-age" aria-invalid="true">
<p id="cat-age-error" class="error">Invalid age.</p>

<!-- Good example (identifies error and suggests fix) -->
<label for="cat-age">Cat's Age:</label>
<input type="text" id="cat-age" aria-invalid="true" aria-describedby="cat-age-error">
<p id="cat-age-error" class="error">Invalid age. Please enter a number between 0 and 30.</p>

<!-- Another good example (with pattern) -->
<label for="cat-birth">Cat's Birth Date:</label>
<input type="text" id="cat-birth" aria-invalid="true" aria-describedby="cat-birth-error cat-birth-desc" pattern="[0-9]{2}/[0-9]{2}/[0-9]{4}">
<span id="cat-birth-desc" class="input-format">Format: MM/DD/YYYY</span>
<p id="cat-birth-error" class="error">Invalid date format. Please enter the date as MM/DD/YYYY (for example: 05/12/2020).</p>

<!-- Live validation example -->
<label for="cat-email">Contact Email:</label>
<input type="email" id="cat-email" aria-describedby="email-error">
<p id="email-error" class="error" role="alert" aria-live="assertive">Please enter a valid email address (e.g., fluffy@cats.com).</p>
```

---

## Notes

<!-- Notes, if any -->

---

## Resources

<!-- Relevant links -->

- [WCAG Understanding Success Criterion 3.3.3](https://www.w3.org/WAI/WCAG21/Understanding/error-suggestion.html)
- [G85: Providing a text description when user input falls outside the required format or values](https://www.w3.org/WAI/WCAG21/Techniques/general/G85)
- [G177: Providing suggested correction text](https://www.w3.org/WAI/WCAG21/Techniques/general/G177)
- [SCR18: Providing client-side validation and alert](https://www.w3.org/WAI/WCAG21/Techniques/client-side-script/SCR18)
- [WAI-ARIA Authoring Practices for Error Messages](https://www.w3.org/WAI/ARIA/apg/patterns/alert/)
