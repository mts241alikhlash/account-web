---
'account-web': minor
---

Match admission-web's shell: upgrade `@mts241alikhlash/ui` to 1.11 and
`web-shared` to 1.3.1, take the shared `theme.css` tokens, and replace the
hand-rolled header with the fixed top bar that carries the account menu
(`NavUser`, with the profile link and the change-password dialog). The launcher
and profile screens come from admission, and the app's own login page follows
the same card and control sizes.

account-web has no sidebar, so `AccountLayout` supplies `SidebarProvider` only
for the context `NavUser` reads, and stacks the header and the page inside it.

`vite.config.ts` excludes `@mts241alikhlash/ui` from the dependency pre-bundle,
as the other apps do, so the package is one module instance in development.
