# Bolt.new

- source_url: https://bolt.new/
- category: developer-tools-ides
- site_slug: bolt-new
- analyzed_at: 2026-06-02
- access_state: public-only
- output_files:
  - design-system-analysis/bolt-new-DESIGN.zh-CN.md
  - design-system-analysis/bolt-new-DESIGN.en-US.md
  - design-system-analysis/bolt-new-preview.html
- observed_pages:
  - label: Home
    url: https://bolt.new/
    access: public
  - label: Pricing
    url: https://bolt.new/pricing
    access: public
  - label: Enterprise
    url: https://bolt.new/enterprise/
    access: public
- known_gaps:
  - Logged-in Builder, workspace, and project editor surfaces were not inspected.
  - Resources dropdown contents were not treated as verified evidence because browser click waiting timed out during inspection.
  - No prompt, email form, login, purchase, upgrade, or account-changing action was submitted.
  - Font conclusions came from computed styles; loaded font entries were not exposed through `document.fonts`.
  - Animations, hover transitions, and some product mock details were not broken down frame by frame.
- notes:
  - Classified as `developer-tools-ides` because Bolt.new is an AI coding and web-app building environment with developer-tool and IDE-like workflows.
  - Preview HTML uses public Bolt.new visual assets and was improved after browser review to avoid placeholder icons and fake brand tiles.
