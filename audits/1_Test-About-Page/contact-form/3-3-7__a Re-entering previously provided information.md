## Bug Summary

- **Success Criterion:** 3.3.7
- **Standard:** A
- **Severity:** 1

<!-- description -->

Forms that require users to re-enter information they've already provided earlier in the same process create unnecessary barriers, particularly for users with cognitive disabilities, memory limitations, or those using assistive technologies.

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

When users have already provided information in a previous step of a multi-step process, implement one of these solutions:

- **Auto-populate fields:** Automatically fill in fields with previously provided information
- **Provide selection options:** Allow users to select from previously entered information
- **Store and retrieve data:** Use web storage, cookies, or server-side storage to maintain data across form steps
- **Unified form view:** Where appropriate, combine related steps into a single view
- **Visual confirmation:** Clearly display previously entered information for reference

This improves usability for everyone, especially those with cognitive disabilities, memory limitations, motor impairments, or using assistive technologies.

### Example

Instead of requiring users to re-enter information about their cat in multiple steps of a form:

- Use the `autocomplete` attribute on form fields to suggest previously entered values
- Implement a dropdown selection showing previously entered cat names with identifying details (e.g., "Whiskers - Adopted June 2024")
- Display a summary panel showing previously entered information about the cat for reference
- Store cat information in browser storage or cookies to retrieve across multiple pages
- Consider combining related cat information fields into a single section rather than spreading across multiple pages
- Use server-side session storage to maintain cat registration information throughout a multi-step process

---

## Notes

<!-- Notes, if any -->

---

## Resources

<!-- Relevant links -->

- [WCAG 2.2 - Success Criterion 3.3.7: Redundant Entry](https://www.w3.org/WAI/WCAG22/Understanding/redundant-entry.html)
- [Technique G221: Provide data from previous form submission](https://www.w3.org/WAI/WCAG22/Techniques/general/G221)
- [Failure F109: Failure of Success Criterion 3.3.7 Redundant Entry due to users having to re-enter previously submitted information](https://www.w3.org/WAI/WCAG22/Techniques/failures/F109)
- [MDN Web Docs: Using the autocomplete attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/autocomplete)
- [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
