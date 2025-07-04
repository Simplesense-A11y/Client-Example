# Dromena.dev Accessibility Testing

Welcome to your accessibility testing repository. This document explains how to effectively use this repository to submit and track accessibility testing requests how to locate and understand test findings.

You'll work exclusively in this repo and the linked project, which is accessible through the repository navigation at the top of this page.

## Repository Structure

```
Repository
├── .github/                      # Contains issue templates (no client action needed)
├── audits/                       # Contains all completed audit findings
│   └── <issue-number>_<title>/   # Directories for each audit request
│       └── <component-name>/     # Subdirectories for each component tested
│           ├── _assets/          # Screenshots documenting failures
│           ├── $component.md     # Component overview
│           └── <wcag-failure>.md # Individual failure documentation
├── README.md                     # This file
└── TEAM.md                       # List of collaborators with access to this repo
```

## Workflow Overview

1. **Submit a request** using the appropriate issue template inside your linked project
2. **Prioritize your requests** by rank-ordering them in the "Backlog" column on the project board
3. **Track progress** of your requests as they move through the workflow columns
4. **Review findings** in the corresponding directories within the `audits` folder
5. **Submit new requests** for retesting after implementing fixes

> [!IMPORTANT]  
> Small, discrete testing requests (like single pages or components) are processed more quickly than large, complex requests.

## Submitting Requests

### Creating Issues

All requests are submitted as GitHub Issues through the Project Board:

1. Navigate to the Project Board (link at the top of the repository)
2. Click "+ Add Item" at the bottom of the "Backlog" column
3. Select "Create new issue"
4. Choose the appropriate issue template:

   | Template                            | Purpose                                         |
   | ----------------------------------- | ----------------------------------------------- |
   | Add or Remove Repository Members    | Request changes to collaborator access          |
   | Accessibility Audit Request         | Request testing of specific components/pages    |
   | Design Accessibility Review Request | Request review of designs before implementation |
   | Accessibility Question              | Ask general questions about accessibility       |

5. Complete all required fields in the issue form
6. Submit the issue

> [!WARNING]  
> Make sure you create an actual issue and not just a draft item on the board. Draft items won't be processed as formal requests. But they're a great way for your team to plan and plot work.

### Prioritizing Requests

After submitting requests, you can prioritize them by:

1. Going to the Project Board view
2. Dragging issues within the "Backlog" column or using the "more actions (...)" button to reorder them
3. Placing highest priority items at the top

> [!NOTE]  
> Our team works on issues from top to bottom within the "Backlog" column. The order directly determines when work begins on each request.

> [!CAUTION]
> Please only move issues within the "Backlog" column. Our team will manage the movement of issues to other columns in the workflow.

## Project Board Workflow

The Project Board uses the following columns to track progress:

| Column      | Description                                                      |
| ----------- | ---------------------------------------------------------------- |
| Backlog     | New requests awaiting processing (client-managed priority order) |
| In Progress | Requests currently being worked on                               |
| Blocked     | Requests that require additional information or clarification    |
| Done        | Completed requests with findings available in the repository     |
| Archive     | Historical requests no longer needing attention                  |

## Best Practices for Effective Testing

### Submit Discrete Requests

> [!TIP]
> Small, focused requests are processed more quickly and efficiently than large, complex requests.

✅ **Recommended**:

- Single component testing (e.g., "Test navigation menu")
- Single page testing (e.g., "Test checkout page")
- Specific feature testing (e.g., "Test form validation")

❌ **Not Recommended**:

- Full site audit (e.g., "Test our entire website")
- Multiple unrelated components in one request
- Vague requests without clear scope

### Provide Complete Information

For each request, please include:

- Clear description of what needs to be tested
- URL(s) of the testing environment
- Any required credentials for access

> [!IMPORTANT]  
> Incomplete information will cause your request to be moved to the "Blocked" column until all necessary details are provided, delaying the testing process.

If an issue becomes blocked, the submitter will be notified using `@username`. You'll be able to fix the issue, notify the team, and then we'll move the issue to the top of the "Backlog" or back into "In Progress".

### Maintain Stable Testing Environments

> [!CAUTION]
> Changes to testing environments during active testing may lead to inconsistent results and extended testing timelines.

- Avoid pushing updates to testing environments during active testing
- If updates are necessary, please inform us in the issue comments
- It's best to have a testing-dedicated environment

## Understanding Test Results

### Audit Structure

After completing an audit, we will:

1. Notify you in the original issue
2. Create a directory structure in the `audits` folder following this pattern:
   ```
   audits/
   └── <issue-number>_<issue-title>/
       └── <component-name>/
           ├── _assets/                   # Screenshots of failures
           ├── $component.md              # Component overview
           └── <wcag-failure>.md          # Detailed failure documentation
   ```

> [!NOTE]  
> Each WCAG failure is documented in a separate file named according to the specific criterion and issue (e.g., `1-1-1__a Improper handling of decorative content.md`).

### WCAG Failure Documentation

Each WCAG failure document contains:

| Section             | Purpose                                                                     |
| ------------------- | --------------------------------------------------------------------------- |
| Bug Summary         | Provides a high-level overview of the accessibility issue                   |
| Success Criterion   | Identifies the specific WCAG guideline violated (1.1.1 Non-text Content)    |
| Standard            | Indicates the WCAG conformance level (A, AA, or AAA)                        |
| Issue Description   | Explains the problem and its impact on assistive technology users           |
| Details             | Contains specific information about the failure instance                    |
| Element Description | Describes the problematic element (empty in this example)                   |
| Element Selector    | Provides technical identifier to locate the element (empty in this example) |
| Steps to Reproduce  | Lists instructions to encounter the issue (empty in this example)           |
| Solution            | Contains remediation guidance                                               |
| Solution Summary    | Explains the general approach to fixing this type of issue                  |
| Example             | Shows code samples of correct and incorrect implementations                 |
| Notes               | Space for additional context-specific information                           |
| Resources           | Lists reference materials and documentation for further reading             |

## Communication

All communication takes place in issue comment threads. When you have questions or need clarification:

1. Navigate to the relevant issue
2. Add your question or comment to the thread
3. Tag specific team members, if needed, using `@username`

> [!IMPORTANT]  
> Please keep all communication within issue threads rather than using external channels to ensure all project information remains accessible to the team.

## Retesting After Fixes

To request retesting after implementing fixes:

1. Create a **new** issue using the "Accessibility Audit Request" template
2. Optionally, reference the original issue number if known
3. Add to the Project Board and prioritize

> [!WARNING]  
> Do not request retesting in comments on closed issues. Always create a new issue for retesting to ensure proper tracking and documentation.

---

If you have questions about this process, please create an issue using the "Accessibility Question" template.
