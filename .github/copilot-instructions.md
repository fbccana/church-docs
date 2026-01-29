# Copilot Instructions - Church Documentation Repository

## Project Overview
This is a **church governance documentation site** built with **MkDocs** and **Material theme**, deployed to GitHub Pages. The repository centralizes the church's constitution, bylaws, policies, and job descriptions in a single-source-of-truth format.

## Architecture & File Organization

### Key Directories
- `docs/` - All site content (Markdown)
  - `jobs/` - Job descriptions organized by department (custodial, ministerial, program, support)
  - `policies/` - Church operational policies
  - `bylaws/` - Governing bylaws and procedures
  - `constitution/` - Foundational doctrinal and structural documents
- `mkdocs.yml` - Site configuration, navigation structure, theme settings
- `docs/jobs/job-template.md` - **Use as template for all new job descriptions**

### Content Patterns

**Job Descriptions** follow strict formatting (see [job-template.md](docs/jobs/job-template.md)):
- Front matter with title (YAML)
- Metadata table: Department, Reports To, FLSA Status, Employment Type, Date
- Sections: Position Summary, Essential Functions (40/35/25% time splits common), Qualifications (Required/Preferred), Physical Requirements, Performance Expectations, Reporting Relationships, Compensation/Benefits, Employment Conditions
- Advanced job files (e.g., [job-support-flc-one.md](docs/jobs/support/job-support-flc-one.md)) include RACI charts and schedule information

**Index Pages** ([docs/index.md](docs/index.md), [docs/jobs/index.md](docs/jobs/index.md)):
- Introductory context explaining purpose and applicability
- Links to related documents
- Ministry philosophy (governance supports ministry clarity and order)

## MkDocs Build & Deployment

**Build Command**: `mkdocs build` (generates static site in `site/` folder)  
**Serve Locally**: `mkdocs serve` (preview at `http://localhost:8000/`)  
**Deployment**: Push to repo → GitHub Actions → GitHub Pages (automatic)

**Theme Configuration** in [mkdocs.yml](mkdocs.yml):
- Material theme with slate scheme, blue-grey primary, amber accent
- Extensions: admonition, toc (with permalinks), footnotes, tables
- Navigation auto-configured from YAML structure

## Critical Conventions

1. **Job Description Metadata**: Always use consistent metadata table format with key fields in column 1, values in column 2
2. **Time Allocations**: Primary/Secondary/Additional responsibilities often broken into % time spent (40/35/25 pattern seen in support roles)
3. **RACI Charts**: Complex multi-stakeholder roles should include RACI responsibility matrix
4. **Bilingual Support**: For roles serving Spanish-speaking congregation, explicitly note bilingual requirements in Qualifications and Responsibilities sections
5. **Cross-linking**: Use relative Markdown links to connect related documents (e.g., job descriptions linking to Policies, Bylaws sections)

## Document Structure Philosophy

All documents should:
- State purpose clearly in introduction or summary section
- Define scope and applicability
- Use consistent formatting with headers, tables, and lists for scannability
- Link to related documents
- Include effective date or last update (as version control, not content)
- Avoid jargon; church context is primary, not legal/technical language

## When Editing/Creating Content

**New Job Descriptions**: 
1. Copy [job-template.md](docs/jobs/job-template.md) structure exactly
2. Place in appropriate subfolder under `docs/jobs/` (custodial, ministerial, program, or support)
3. Add entry to `mkdocs.yml` nav under the appropriate job category
4. Use percentage-based time allocations for realistic responsibility distribution

**Policy/Bylaw Updates**:
- Maintain consistent section structure across related documents
- Update date field when content changes
- Preserve historical context (these are governing documents, not disposable)

**Navigation Changes**:
- Edit `mkdocs.yml` nav section to match physical file structure
- Test with `mkdocs serve` before committing

## Common Tasks & Commands

| Task | Command |
|------|---------|
| Preview site locally | `mkdocs serve` |
| Build for deployment | `mkdocs build` |
| Validate YAML structure | Parse `mkdocs.yml` via editor or linter |
| Check links in Markdown | Review relative paths match actual files |

## Key Files as References

- [job-support-flc-one.md](docs/jobs/support/job-support-flc-one.md) - Comprehensive example with RACI chart, schedule details, and multiple responsibility sections
- [job-support-clerk.md](docs/jobs/support/job-support-clerk.md) - Bilingual role example with time allocations and complex stakeholder relationships
- [mkdocs.yml](mkdocs.yml) - Defines complete site structure and theme
- [GEMINI.md](GEMINI.md) - Original system instructions for AI assistant work on this repo

## Special Notes

- All documents use standard Markdown; no custom syntax
- Ministry context: these documents serve transparency, accountability, and unity—not just bureaucracy
- No code in this repository; purely documentation and configuration
- Site builds automatically on push via GitHub Pages integration

