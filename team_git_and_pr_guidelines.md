# Team Git & Pull Request Guidelines

## 1. Commit Message & PR Title Convention

To maintain a clean, readable, and trackable project history, all Git commit messages and Pull Request titles **must** follow this exact format:

**Format:** `<type> (<JIRA-ID>): <description>`

### Allowed Types:
*   **`feat`**: A new feature or product enhancement.
*   **`fix`**: A bug fix.
*   **`docs`**: Documentation-only changes (README, inline comments, wikis).
*   **`refactor`**: A code change that neither fixes a bug nor adds a feature (e.g., restructuring code).
*   **`perf`**: A code change that improves performance.
*   **`test`**: Adding missing tests or correcting existing tests.
*   **`infra`**: Changes to infrastructure, deployment scripts, or Dockerfiles.
*   **`build`**: Changes that affect the build system or external dependencies (npm, pip, maven).
*   **`ci`**: Changes to CI/CD configuration files and scripts (GitHub Actions, GitLab CI, Jenkins).
*   **`chore`**: Routine tasks, maintenance, or tooling changes that don't modify source or test files.
*   **`style`**: Changes that do not affect the meaning of the code (whitespace, formatting, missing semi-colons).

**Examples:**
*   `feat (JR-123): add Google OAuth login`
*   `fix (JR-124): resolve null pointer exception on checkout page`
*   `infra (JR-125): upgrade Terraform AWS provider to v4.0`

## 2. Merge Strategy: Squash and Merge ONLY

All pull requests must be squash merged. This keeps the main branch history clean with one commit per feature/fix. 

* **Repo Admin Action:** Go to Repository **Settings** > **Pull Requests** and uncheck "Allow merge commits" and "Allow rebase merging", leaving only "Allow squash merging" enabled.
* **Developer Action:** Ensure your PR title perfectly matches the commit message format, as GitHub/GitLab will use the PR title as the final squashed commit message.

## 3. Pull Request Template

Create a file named `.github/pull_request_template.md` (for GitHub)

```markdown
## Description
<!-- Provide a brief summary of the changes introduced by this PR. -->
<!-- Explain WHY this change is needed, not just WHAT was changed. -->

## Jira Ticket
<!-- Link to the Jira ticket -->
[PROJ-XXX](https://mign-jp.atlassian.net/browse/TICKET-XXX)

## Checklist
<!-- Review this list and mark items with an [x] as you complete them -->
- [ ] My PR title follows the team convention (`<type> <JIRA-ID>: <message>`).
- [ ] I have performed a self-review of my own code.
- [ ] I have added tests that prove my fix is effective or that my feature works.
- [ ] New and existing unit tests pass locally with my changes.
- [ ] I have updated the documentation accordingly (if applicable).

## Screenshots / Screen Recordings (if applicable)
<!-- Add UI screenshots or terminal output demonstrating the changes -->
```