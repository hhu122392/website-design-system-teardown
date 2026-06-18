# Pinduoduo Sign-in Campaign Teardown

- source_url: https://mobile.yangkeduo.com/havana_mianfei_packet.html
- category: ecommerce-retail
- site_slug: pinduoduo-signin-campaign
- analyzed_at: 2026-06-18
- access_state: public-mobile-page-with-personalized-state
- output_files:
  - design-system-analysis/pinduoduo-signin-campaign-DESIGN.zh-CN.md
  - design-system-analysis/pinduoduo-signin-campaign-DESIGN.en-US.md
  - design-system-analysis/pinduoduo-signin-campaign-preview.html
  - design-system-analysis/pinduoduo-signin-campaign-AUDIT.md
- observed_pages:
  - label: Pinduoduo home "Other" modal entry
    url: https://mobile.yangkeduo.com/index.html
    access: public
  - label: Sign-in campaign main page
    url: https://mobile.yangkeduo.com/havana_mianfei_packet.html
    access: public page with personalized account display
  - label: Top menu popover
    url: https://mobile.yangkeduo.com/havana_mianfei_packet.html
    access: public page with personalized account display
  - label: Activity rules modal
    url: https://mobile.yangkeduo.com/havana_mianfei_packet.html
    access: public page with personalized account display
  - label: Medical category selected state
    url: https://mobile.yangkeduo.com/havana_mianfei_packet.html
    access: public page with personalized feed
- known_gaps:
  - Did not click draw, payout detail, product purchase, task claim, or order CTA entries because they may create account or commerce side effects.
  - Exact account balance and share/query parameters are intentionally redacted from deliverable documents and preview.
  - Product feed content is personalized and may change by account, time, category, and scroll depth.
- notes:
  - Source evidence files are in screenshots/ and evidence/.
  - The analysis focuses on the observed sign-in activity page design system, not official Pinduoduo brand guidelines.
