# Recommended Packages

| Package | Purpose | Notes |
|---------|---------|-------|
| `flutter_bloc` | State management | Required |
| `equatable` | Value equality for BLoC events/states | Required alongside `flutter_bloc` |
| `intl` | Currency/number formatting | Optional, recommended for displaying prices and the order total |

Beyond these, any standard Flutter package is fine. There's no live API in this project, so you won't need an HTTP client at either tier.

---

## Not Allowed

These are explicitly off-limits — see [`06-ground-rules.md`](06-ground-rules.md) for why:

- **GetX, Provider, Riverpod** (or any other state management package) for cart state — the whole point of this project is demonstrating BLoC
- **External UI kits** — every widget must be built from scratch

---

Add the packages you need to your `pubspec.yaml` under `dependencies:`, then run:

```bash
flutter pub get
```

See [`00-getting-started.md`](00-getting-started.md) if you haven't initialised your Flutter project yet.

## Next Steps

- Building Tier 1 only? Head to [`02-tier-1-base.md`](02-tier-1-base.md) for the architecture you'll need these packages for
- Building Tier 2? See [`03-tier-2-intermediate.md`](03-tier-2-intermediate.md) for the Repository layer these packages support
