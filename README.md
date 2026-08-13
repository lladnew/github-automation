# Shared GitHub automation

Reusable workflows for repositories owned by `lladnew`.

## Project lifecycle

`project-lifecycle.yml` keeps a GitHub Projects v2 item synchronized with issue
and pull-request activity. Caller repositories provide the user-owned project
number and an encrypted `PROJECTS_TOKEN` secret with Projects read/write
access.

Supported transitions:

- issue assigned: `In Progress`
- linked pull request opened, including a draft: `In Review`
- pull request marked ready for review: `In Review`
- merged pull request: `Done`
- unmerged pull request closed: `Ready`

Pull requests must link issues with a GitHub closing keyword such as
`Closes #123`.

The workflow also reads standardized planning answers from issue forms and
sets matching `Priority`, `Area`, `Effort`, and `Target` project fields.
