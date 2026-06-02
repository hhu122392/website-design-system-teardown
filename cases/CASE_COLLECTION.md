# Case Collection

This folder stores completed website design-system teardown cases for reuse and future repository updates.

The category structure follows the public collection pattern used by `VoltAgent/awesome-design-md`: cases are grouped by product domain so new examples can be found and pushed cleanly.

## Category Folders

- `ai-llm-platforms/`
- `developer-tools-ides/`
- `backend-database-devops/`
- `productivity-saas/`
- `design-creative-tools/`
- `fintech-crypto/`
- `ecommerce-retail/`
- `media-consumer-tech/`
- `automotive/`
- `retro-web-nostalgia/`
- `uncategorized/`

Use `uncategorized/` only when the site does not clearly fit any folder. Move it later when a better category is chosen.

## Case Folder Shape

Each case should live at:

```text
cases/<category>/<site-slug>/
```

Recommended files:

```text
metadata.md
design-system-analysis/<site-slug>-DESIGN.zh-CN.md
design-system-analysis/<site-slug>-DESIGN.en-US.md
design-system-analysis/<site-slug>-preview.html
screenshots/
```

Optional files:

```text
design-system-analysis/<site-slug>-preview-dark.html
design-system-analysis/<site-slug>-preview-light.html
notes.md
```

Use `preview-dark.html` or `preview-light.html` only when the case has a real alternate canvas or theme worth keeping as a separate file.

## Metadata Template

Use this shape in `metadata.md`:

```markdown
# <Case Name>

- source_url:
- category:
- site_slug:
- analyzed_at:
- access_state: public-only | logged-in-assisted | mixed | blocked
- output_files:
  - design-system-analysis/<site-slug>-DESIGN.zh-CN.md
  - design-system-analysis/<site-slug>-DESIGN.en-US.md
  - design-system-analysis/<site-slug>-preview.html
- observed_pages:
  - label:
    url:
    access: public | logged-in
- known_gaps:
  - 
- notes:
  - 
```

## Collection Rules

- Do not store passwords, cookies, tokens, account IDs, personal data, or screenshots that expose private user information.
- If a case used logged-in inspection, record only design-relevant observations and mark `access_state`.
- Keep filenames stable so later sync scripts or repository pushes can find files reliably.
- Preserve the generated `design-system-analysis/` folder inside each case. Do not flatten generated files into the case root.
- Prefer one case per folder. Do not mix multiple brands or websites in one case folder.
- Keep the category index clean: when a new category is needed, add it to this file and create a folder.
