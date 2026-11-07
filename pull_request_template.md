## What does this PR do?

<!-- A clear description of the change and why it's needed. Fixes # -->

## The rules

Check each one, or explain why it doesn't apply.

- [ ] **No RA calls from client requests.** Pages only read stored data, and any new RA call goes through the shared rate limiter.
- [ ] **Same everywhere.** No hardcoded colors or sizes (tokens only); stats come from the API. For web features, the issue notes what mobile needs.
- [ ] **Privacy and opt-outs.** Private profiles and Untracked accounts stay out of global and social features.
- [ ] **Accessible.** Keyboard and screen reader checked; charts have a text summary; works at 200% text and with reduced motion.

## Testing

<!-- How did you verify this? Tests use recorded RA fixtures, never the live API. For UI changes, include screenshots in light and dark themes. -->

## Spec

- [ ] This matches `docs/spec.md`, or I updated the spec in this PR.
