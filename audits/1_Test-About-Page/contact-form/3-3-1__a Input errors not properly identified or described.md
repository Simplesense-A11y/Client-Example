## Bug Summary

- **Success Criterion:** 3.3.1 Error Identification
- **Standard:** A
- **Severity:** 1

<!-- description -->

Form validation errors are not clearly identified, not programmatically associated with input fields, or lack descriptive text explaining the error and how to fix it.

---

## Details

### Element Description

<!-- Textual description of affected element's or component's location, state, etc. and screenshots-->

All input fields when in error

### Element Selector

<!-- CSS or JS selector -->

```css
.container .form.contact input
```

### Steps to Reproduce

<!-- Steps required to reproduce the bug -->

Submit the form with empty input values

---

## Solution

### Solution Summary

When a form contains input errors, these errors must be:

1. **Clearly identified:** The error must be visually apparent and programmatically determinable.
2. **Properly associated:** Each error must be programmatically linked to its corresponding form field.
3. **Descriptive:** Error messages must explain what went wrong and how to fix it.

**Implementation approaches:**

- **Inline validation:** Error messages appear directly adjacent to the form control with the error, providing immediate context.
- **Page-level errors:** A summary list of all errors is presented at the top of the form, often with links to the corresponding fields.

**Best practices:**

- **Use both approaches together:** For complex forms, implement both inline and page-level errors to provide multiple ways for users to understand and resolve issues.
- **Focus management:** When validation triggers, set focus appropriately—either to the first error in the form or to the error summary.
- **Error timing:** Consider when to validate—on submit, on blur, or as the user types.
- **Non-visual users:** Ensure screen reader users are notified of errors through proper ARIA attributes and live regions.

### Example

html

```html
<!-- Page-level error summary -->
<div role="alert" aria-live="assertive" id="form-errors" class="error-summary">
  <h2>Please correct the following 2 errors:</h2>
  <ul>
    <li><a href="#cat-name">Cat's name is required</a></li>
    <li><a href="#cat-age">Cat's age must be a number between 0 and 30</a></li>
  </ul>
</div>

<!-- Form with inline errors -->
<form novalidate aria-describedby="form-errors">
  <!-- Field with inline error -->
  <div class="form-group">
    <label for="cat-name">Cat's Name: <span aria-hidden="true">*</span></label>
    <span class="sr-only">required</span>
    <input 
      type="text" 
      id="cat-name" 
      name="catName" 
      aria-invalid="true" 
      aria-describedby="cat-name-error"
      required
    >
    <!-- Inline error message -->
    <div id="cat-name-error" class="error-message" role="alert">
      <img src="alert-icon.svg" alt="" aria-hidden="true">
      <span>Please enter your cat's name (required field)</span>
    </div>
  </div>
  
  <!-- Another field with inline error -->
  <div class="form-group">
    <label for="cat-age">Cat's Age (years):</label>
    <input 
      type="number" 
      id="cat-age" 
      name="catAge" 
      aria-invalid="true" 
      aria-describedby="cat-age-error"
      min="0"
      max="30"
    >
    <!-- Inline error message -->
    <div id="cat-age-error" class="error-message" role="alert">
      <img src="alert-icon.svg" alt="" aria-hidden="true">
      <span>Please enter a valid age between 0 and 30 years</span>
    </div>
  </div>
  
  <button type="submit">Register My Cat</button>
</form>

<!-- JavaScript for handling both error types -->
<script>
  // Example code to handle form submission and validation
  document.querySelector('form').addEventListener('submit', function(e) {
    let hasErrors = false;
    const errorSummary = document.getElementById('form-errors');
    const errorList = errorSummary.querySelector('ul');
    
    // Clear previous errors
    errorList.innerHTML = '';
    
    // Validate cat name (example)
    const catName = document.getElementById('cat-name');
    if (!catName.value.trim()) {
      hasErrors = true;
      // Add to error summary (page-level)
      errorList.innerHTML += '<li><a href="#cat-name">Cat\'s name is required</a></li>';
      // Show inline error
      document.getElementById('cat-name-error').setAttribute('aria-hidden', 'false');
    }
    
    if (hasErrors) {
      e.preventDefault();
      errorSummary.style.display = 'block';
      // Set focus to the error summary
      errorSummary.focus();
    }
  });
</script>
```

---

## Notes

<!-- Notes, if any -->

---

## Resources

- [WCAG 3.3.1 Error Identification](https://www.w3.org/WAI/WCAG21/Understanding/error-identification.html)
- [G83: Providing text descriptions to identify required fields that were not completed](https://www.w3.org/WAI/WCAG21/Techniques/general/G83)
- [ARIA21: Using Aria-Invalid to Indicate An Error Field](https://www.w3.org/WAI/WCAG21/Techniques/aria/ARIA21)
- [G84: Providing a text description when the user provides information that is not in the list of allowed values](https://www.w3.org/WAI/WCAG21/Techniques/general/G84)
- [G85: Providing a text description when user input falls outside the required format or values](https://www.w3.org/WAI/WCAG21/Techniques/general/G85)
- [WAI-ARIA Authoring Practices: Error Message](https://www.w3.org/WAI/ARIA/apg/patterns/alert/)
