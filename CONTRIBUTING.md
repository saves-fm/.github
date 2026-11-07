# Contributing to saves.fm

Thanks for helping build saves.fm. This covers how to contribute, whether you write code, design, test, translate, or just play a lot of retro games and have opinions.

Please read the [Code of Conduct](CODE_OF_CONDUCT.md) before taking part.

---

## Ways to contribute

### Not a developer? Still useful.
- **RetroAchievements players:** tell us what you'd want to see about your own history, and file issues when stats look wrong. You know your play sessions better than any algorithm.
- **Designers:** the design system is shared between web and mobile through design tokens, so improvements there reach every screen.
- **Translators:** saves.fm launches in English but every string lives in translation files from day one. Translation work opens up after v1.0.

### Developers
- Pick up an issue from the [backlog](https://github.com/saves-fm/saves/issues). Every issue is in a version milestone, and `good first issue` marks the friendliest ones.
- The full plan, architecture and data model are in [`docs/spec.md`](https://github.com/saves-fm/saves/blob/main/docs/spec.md). Read the section for your issue's milestone first.

---

## Before you start

1. **Comment on the issue** (or open one) before starting anything non-trivial, so work isn't duplicated.
2. **Check the spec.** If your change needs to differ from it, say so in the issue and update the spec in the same PR.

---

## The rules

Every change must keep these true:

1. **Never call RetroAchievements from a client request.** Pages read only data that's already stored. All RA calls go through the shared rate limiter, and nothing adds API keys to get more capacity.
2. **Same experience everywhere.** Colors, type, spacing and motion come from `packages/tokens`, and stats are computed by the API, so web and mobile never drift. A web feature notes what its mobile version needs.
3. **Respect privacy and opt-outs.** Private profiles and Untracked RA accounts never appear in global charts, game pages, Player 2, recommendations or other people's feeds. Users never share API keys or passwords.
4. **Accessible by default.** WCAG 2.2 AA on web and mobile: keyboard and screen reader support, text summaries for charts, 200% text, and reduced motion.

---

## Dev setup

Setup instructions arrive with the monorepo in [v0.1.0](https://github.com/saves-fm/saves/milestone/1). The stack is pnpm workspaces (React + Vite web, Hono on Cloudflare Workers) and Flutter with Melos.

## Pull requests

- Reference the issue (`Fixes #123`).
- Tests run in CI and never call the live RA API; use the recorded fixtures.
- Strings go through the translation catalog; no hardcoded colors or sizes.
