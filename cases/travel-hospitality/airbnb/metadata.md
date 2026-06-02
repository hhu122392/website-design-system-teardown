# Airbnb

- source_url: https://zh.airbnb.com/
- category: travel-hospitality
- site_slug: airbnb
- analyzed_at: 2026-06-02
- access_state: public-only
- output_files:
  - design-system-analysis/airbnb-DESIGN.zh-CN.md
  - design-system-analysis/airbnb-DESIGN.en-US.md
  - design-system-analysis/airbnb-preview.html
- observed_pages:
  - label: Home / Homes
    url: https://zh.airbnb.com/
    access: public
  - label: Experiences
    url: https://zh.airbnb.com/experiences
    access: public
  - label: Services
    url: https://zh.airbnb.com/services
    access: public
  - label: Host homes
    url: https://zh.airbnb.com/host/homes
    access: public
  - label: Help
    url: https://zh.airbnb.com/help
    access: public
  - label: Room detail
    url: https://zh.airbnb.com/rooms/1446929417046820432
    access: public
- known_gaps:
  - The user explicitly asked not to log in, so wishlist, trips, messages, account menu, logged-in booking flow, and host dashboard surfaces were not inspected.
  - No search, booking, payment, login, or state-changing action was submitted.
  - Only one public room-detail sample was opened, and it loaded limited detail content in this environment.
  - The Services page exposed limited service-card content in the public state observed.
  - Remote source images and navigation icons are loaded from public Airbnb URLs.
- verification:
  - Preview HTML was checked in the in-app browser at localhost.
  - Homes / Experiences / Services navigation icons use observed Airbnb public tab assets.
  - Tab underline state was verified for #services and real-click transition to Experiences.
  - Preview image loading was checked with zero failed images after the final fix.
- notes:
  - This is an independent design-system analysis and not an official Airbnb guideline.
