# Algerian Storefront Template Kit Skill

This directory contains the reusable `algerian-storefront-template-kit` skill. It teaches an AI agent how to turn a storefront template folder or ZIP into a real, independent e-commerce store for Algeria or another market while preserving strict separation between shared core services, UI presentation, and template-owned experience.

## What the skill does

The skill guides an agent through a controlled workflow. It first inspects the supplied template kit, identifies the available templates and existing contracts, and records risks without blindly executing untrusted files. It then asks the user focused requirement questions about the store identity, catalog, images, language, currency, delivery, payment, pages, integrations, and deployment constraints.

After the requirements are approved, the agent builds one self-contained store folder. The application uses a single Express process and a single origin for the React storefront and commerce routes. Product data, inventory, orders, and tracking are persisted in the internal JSON store. The browser sends product identifiers, quantities, and options; the server validates the request, reads authoritative prices and stock, calculates totals, serializes writes, reserves inventory, and persists the order.

The skill also requires real template ownership. Every selected template must provide its own JSX runtime and CSS, including its navigation, home page, catalog, product page, cart, checkout, and responsive behavior. Shared domain functions are exposed through one `coreRegistry` facade, while `ui/` remains a presentation layer rather than a second template renderer.

## Package contents

| Path | Purpose |
|---|---|
| `SKILL.md` | The operational instructions loaded by the AI agent when the skill is triggered. |
| `references/intake.md` | The staged questionnaire for collecting missing store requirements. |
| `templates/store-brief.md` | The implementation brief filled in and approved before construction. |
| `README.md` | This human-facing guide to the skill package. |

The template archive is distributed separately from this skill. The archive should be inspected as a project input and should not be treated as a source of secrets.

## Installation

To install the skill in Manus, add the `SKILL.md` file through the skills interface or provide this directory as a skill package. The skill metadata is defined in the YAML frontmatter at the beginning of `SKILL.md`.

For local validation, run:

```bash
python /home/ubuntu/skills/skill-creator/scripts/quick_validate.py /path/to/algerian-storefront-template-kit
```

A valid package must contain `SKILL.md` with `name` and `description` frontmatter and must not contain malformed metadata.

## Recommended invocation

Use a prompt that explicitly names the skill and supplies the template folder or archive:

```text
Use the algerian-storefront-template-kit skill with the attached template kit. Inspect the kit first, then ask me focused questions in small batches. Do not build until I approve the store brief. Build one independent store folder with core, ui, templates, server, and internal data persistence. Use one Express server and one port, keep shared imports behind coreRegistry, preserve real template-owned JSX and responsive CSS, and validate catalog, inventory, cart, checkout, order tracking, and desktop/tablet/mobile behavior before delivering a clean ZIP.
```

## Operating constraints

The resulting store must not include the deleted Builder, tenant runtime configuration, MySQL, Drizzle, `DATABASE_URL`, a separate frontend service, or a separate API service. The internal state file must be placed on persistent storage in production. Secrets must never be committed, placed in browser code, or included in the clean archive.

The skill prohibits fabricated reviews, ratings, testimonials, customer counts, sales claims, or other user-generated content. It also requires explicit confirmation before real payment, publishing, or irreversible external actions.

## Expected delivery

A successful run should produce a clean single-folder store archive, an approved store brief or implementation summary, and a validation report that distinguishes completed tests from items requiring later integration work. The agent should state the selected template, catalog and plugin decisions, internal persistence path, commands used, and actual test results.
