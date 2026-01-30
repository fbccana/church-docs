# Copilot Instructions — Church Documents (Actionable Guide)

## Quick summary
- Purpose: single-source church governance docs built with **MkDocs + Material**. Changes are content edits (Markdown) and navigation updates in `mkdocs.yml`.
- Primary folders: `docs/` (content), `docs/jobs/` (job descriptions by department), and `mkdocs.yml` (site nav and theme).

## How to be immediately productive
- Find examples: `docs/jobs/job-template.md` (canonical template), `docs/jobs/support/job-support-flc-one.md` (complex example), `docs/jobs/support/job-support-clerk.md` (bilingual example).
- Common commands:
  - Preview: `mkdocs serve` (http://localhost:8000/)
  - Build static site: `mkdocs build` (output -> `site/`)
  - Quick commit/push helper: `./up.sh` (interactive script in repo root)

## Editing & adding content (practical rules)
- New job files: copy `docs/jobs/job-template.md` and save under `docs/jobs/<category>/job-<category>-<slug>.md` (e.g., `job-support-flc-one.md`).
- Metadata: maintain the metadata block/table (Department, Reports To, FLSA Status, Employment Type, Date). Update `Date` on edits.
- Conventions to preserve:
  - Time allocations commonly use 40/35/25 or 35/35/30 split for Primary/Secondary/Additional duties; mirror existing examples when possible (see `job-support-flc-one.md`).
  - Include RACI tables for multi-stakeholder roles where appropriate.
  - Mark bilingual roles explicitly in Qualifications and Responsibilities (e.g., `job-support-clerk.md`, `job-support-media.md`).
  - Use full date format `December 17, 2025` for the `Date` metadata field across files for consistency.
  - Add a `Schedule Information` section for roles with regular schedules; for temporary/as-needed roles, state `Temporary / As-needed` and note on-call expectations.
  - Financial roles must include a `Critical Internal Controls` or equivalent section describing dual authorization, segregation of duties, reconciliation, and bonding requirements (see `job-support-financial.md`).
- Navigation: when adding/removing files, update `mkdocs.yml` nav (see the Jobs → Support section as the pattern). Run `mkdocs serve` to verify the nav and links.

## QA checklist before opening a PR ✅
1. Copy from `job-template.md` when creating job descriptions.
2. Run `mkdocs build` and fix any link warnings or missing assets.
3. Run `mkdocs serve` and visually verify page layout, tables, and nav order.
4. Ensure cross-links use relative paths and are valid from the file's location.
5. Update `Date` metadata and `mkdocs.yml` nav if file is new.

## Tone & content expectations
- Keep language clear, non-legal, ministry-focused, and accessible.
- Documents state purpose, scope, and effective date near the top.
- Preserve existing formatting patterns (tables for metadata, headings for sections).

## Where to look for edge cases
- Complex examples with RACI and schedule sections: `docs/jobs/support/job-support-flc-one.md`.
- Language-sensitive examples: `docs/jobs/support/job-support-clerk.md`.
- Configuration: `mkdocs.yml` (nav and theme).

## Example small PR description template
- Title: `docs(jobs): add job-support-<slug> for <role>`
- Body: one-sentence summary, files changed, verification steps (mkdocs build + serve pass).

---
If you'd like, I can apply this condensed instruction file in `.github/copilot-instructions.md` now and iteratively refine any missing specifics. Please point out any areas you'd like emphasized or left out.
