# README

## Repo and Project Structure

[Dromena.dev](https://www.dromena.dev/) is built on top of [GitHub's Projects](https://docs.github.com/en/issues/planning-and-tracking-with-projects/learning-about-projects/about-projects). This is a view into this repo and its issues.

There is no juggling pull requests or code reviews here. The repo primarily contains this README, and that's about it.

Every request for an accessibility audit or design review starts as an issue. These can be accessed through the repo, but the repo's Project is setup to make managing requests and monitoring progress much easier.

The Project is accessible through the `nav` labelled "Repository".

The project contains several views:

- **Request Board:** Used to submit requests for accessibility audits/tests and design reviews
- **Client Bug Board:** A list of accessibility bugs found during audits/tests
- **Client Table:** A highly-customizable and filterable table showing whatever issues you'd like

There are also two views prefixed with `[INTERNAL]`:

- **[INTERNAL] Auditor Bug Board:**
- **[INTERNAL] Auditor Table:**

These `[INTERNAL]` views are used by the Dromena.dev team for project management. You'll never need to work in here. Feel free to take a peek, but please be mindful not to modify any of the settings or issues.

> **📢 If you accidentally break it:**
>
> Each view's columns is created using the filter combobox with a unique value. If you accidentally modify the value, don't worry! The sections below contain the value you can copy and paste to revert the

### Request Board:

> **📢 If you accidentally break it:**
>
> `-status:"Bug Draft","Bug Internal Review","Bug Open","Bug Fixed","Bug Resolved"`

The Request Board has 4 columns:

1. **Todo:** Your rank-ordered requests for audits/tests or design reviews ready to be worked
2. **In Progress:** Requests that are currently being worked
3. **Blocked:** Requests that need your attention in order to move forward
4. **Done:** Completed requests with links to bugs and other relevant information

### Client Bug Board

> **📢 If you accidentally break it:**
>
> `-status:Todo,"In Progress",Blocked,Done,"Bug Draft","Bug Internal Review"`

The Client Bug Board has 3 columns: 

1. **Bug Open:** Accessibility bugs found in audits/tests that are ready for you to address
2. **Bug Fixed:** Bugs you've addressed and are ready to be reviewed
3. **Bug Resolved:** Bugs that have been solved

### Client Table

The Client Table is totally customizable. You can add toggle, filter and sort columns to build a view of your requests and bugs however you'd like. 

Please be mindful of any of the properties you modify as changing their values may have unintended consequences across request and bug issues. The best way to use this view is as a "readonly" table.
