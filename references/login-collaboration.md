# Login Collaboration

Use this reference when a target website hides important UI behind login, paywall, invite-only access, checkout state, workspace membership, or a private app shell.

## Decision Rule

Start with public pages. Ask for login help only when the public surface is not enough to fairly analyze the site's design system.

Ask for user assistance when any of these are true:

- The core product UI is behind login.
- Public pages are mostly marketing, but the user asked for product/app design teardown.
- Key components such as dashboards, settings, editor, checkout, trading, workspace, or account flows are unavailable publicly.
- The site changes significantly after login and that change matters for the design system.

Do not ask for login help when public pages already show enough design evidence for the requested scope.

## How To Ask

Ask briefly and specifically:

- Explain which surface is hidden.
- Explain why it matters for the teardown.
- Ask the user to log in themselves in the browser.
- Do not ask the user to paste passwords, codes, cookies, tokens, or private account data into chat.

Example:

```text
这个网站的核心产品界面在登录后，我现在只能看到营销页。为了拆得完整，你可以在浏览器里自己登录一下；我不会让你把密码或验证码发给我。登录完成后我继续看界面结构、颜色、字体和组件，不记录私人内容。
```

## Safety Rules

- Never request credentials in chat.
- Never copy private user data into the output.
- Never submit forms, change settings, make purchases, trade, send messages, or mutate account state unless the user explicitly asks and confirms the exact action.
- Prefer read-only inspection of design patterns.
- If private data appears on screen, use generic labels such as `Account metric`, `Private item`, or `User data hidden`.
- If the user declines or cannot log in, continue with public pages and record the limitation in Known Gaps.

## Output Requirement

When login affects the analysis, include the access state in both Markdown documents:

- `observed_pages`: mark whether pages were public or logged-in.
- `Known Gaps`: state which logged-in surfaces were not inspected.
- `description` and prose: do not imply private/app surfaces were observed if they were not.

