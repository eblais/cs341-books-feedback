# Maintainer workflow

The public issue is the shared record of reader feedback. Book edits and review
take place in the private source repository. The `Label issues by book` workflow
maintains book labels automatically; no book build or Pages deployment runs here.

## Labels

Create these labels through **Issues → Labels → New label**. Names must match
exactly. The colors are suggestions. Labels are repository settings; this file
does not create them automatically.

| Name | Color | Description |
| --- | --- | --- |
| `error` | `D73A4A` | Possible error in the text, mathematics, or links |
| `clarity` | `D4C5F9` | A passage that needs a clearer explanation |
| `suggestion` | `A2EEEF` | Proposed addition or improvement |
| `needs-triage` | `FBCA04` | Awaiting an initial maintainer review |
| `reference-notes` | `1D76DB` | Concerns the Reference Notes |
| `workbook` | `0E8A16` | Concerns the Workbook |
| `awaiting-publication` | `F9D0C4` | Changed in the source; public PDF still needs updating |

The forms apply `needs-triage` and one category label immediately. Once the
`Label issues by book` workflow finishes, it adds the book labels as follows:

| Book selection | Book labels |
| --- | --- |
| Reference Notes | `reference-notes` |
| Workbook | `workbook` |
| Both books | `reference-notes`, `workbook` |

The workflow runs when an issue is opened, edited, or reopened. It reads the
`### Book` section of the submitted issue body and synchronizes only the two
book labels. Other labels are preserved. If the section is missing or its value
is unrecognized, the workflow leaves all labels unchanged.

To correct a book selection after submission, edit the issue body and change
the text below `### Book` to one of the three choices above. Manually changing a
book label alone can be undone by a later edit or reopening. If you rename the
form's Book heading, dropdown options, or book labels, update the workflow too.

Existing issues are not automatically processed when the workflow is installed.
Edit their issue body and save a change, or reopen them, to trigger it.

## Reviewing reports

During a teaching term, aim to review new reports weekly. Agree which instructor
is checking the queue; assign each accepted item to the person handling it.

1. Read the report, check the passage, and acknowledge the feedback. Check the
   automatically applied book labels and correct the category if needed.
2. Ask for more detail if necessary. Remove `needs-triage` once an initial review
   and next step have been recorded. Use the issue comments for decisions.
3. Keep accepted work open and assign an instructor. Leave longer-term suggestions
   open with a brief explanation of when they will be reconsidered.
4. For a duplicate, link the original issue and close the duplicate as not planned.
   For a suggestion you decide not to pursue, explain why and close as not planned.
   If the text is already correct, explain the reasoning; consider whether the
   confusion itself suggests a clarity improvement.

## Editing and publishing

1. Create a branch and pull request in the private source repository. Include the
   full public issue URL in the pull request description, for example
   `Related feedback: https://github.com/eblais/cs341-books-feedback/issues/12`.
   Issue 12 is illustrative; use the actual report's URL.
2. Review the proposed edit and the built PDF, then merge the pull request.
3. Apply `awaiting-publication` to the public issue and leave a short update.
4. Publish through the source repository's existing manual publishing workflow.
5. Check the updated public PDF. Reply on the public issue with what changed,
   where to find it, and the publication date. Remove `awaiting-publication` and
   close the issue as completed.

Avoid `Fixes`, `Closes`, or `Resolves` followed by the public issue reference in
private pull requests or commit messages for this workflow. GitHub can close
the public issue when the change reaches the default branch, before the PDF has
been published. Use an ordinary link and close the report after publication.

Readers cannot see private pull request details. The public reply should describe
the outcome without requiring access to a private link. If a correction was
already published before the report arrived, point to the current PDF and close
the report after checking it.

## Keeping the workflow manageable

Use issue comments for broader suggestions at first. Enable Discussions later
if open-ended editorial conversations become frequent, and create linked issues
for the concrete changes you decide to make.

If feedback arrives through email or another course channel, record actionable
items here when appropriate. Summarize the concern without copying personal
details or private messages. Do not promise anonymous reporting through GitHub.

When ownership or hosting changes, update the public book URL and feedback links
in this repository, the download page, and both PDFs. Grant each incoming
maintainer access to both repositories as appropriate; access is managed
separately for each repository.
