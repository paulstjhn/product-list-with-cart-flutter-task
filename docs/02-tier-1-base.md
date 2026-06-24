# Tier 1 — Base

## Goal

Deliver a working, functionally complete app. All eight core features must work. Code quality matters — no spaghetti logic dumped inside widgets.

This tier is required for every mentee. See [`01-overview.md`](01-overview.md) for the 8 core features that must work correctly — everything below is about *how* you build them.

---

## Technical Requirements

### State Management

- Use **BLoC** (`flutter_bloc`) for cart state — no `setState` for cart logic
- `CartBloc` must handle these events at minimum:
  - `AddToCart`
  - `RemoveFromCart`
  - `IncrementQuantity`
  - `DecrementQuantity`
  - `ResetCart`
- `CartState` must expose: list of cart items, item count, order total

### Data

- Product data must come from a **local** source — a hardcoded list, a local JSON asset, or a Dart model file
- Define a `Product` model class with: `id`, `name`, `category`, `price`, `imageAsset`
- Define a `CartItem` model class with: `product`, `quantity`

### Widget Structure

- `ProductCard` — reusable widget for a single product
- `CartItemTile` — reusable widget for a single cart item
- `OrderConfirmationDialog` — shown via `showDialog` when order is confirmed
- No business logic inside widget `build` methods

### Folder Structure

Your project must be organized. The exact structure is flexible, but it must reflect intent:

| Folder | What goes here |
|--------|----------------|
| `lib/models/` | `Product`, `CartItem` data classes |
| `lib/bloc/` | `CartBloc`, `CartEvent`, `CartState` |
| `lib/data/` | Local product data / mock source |
| `lib/widgets/` | Reusable widget components |
| `lib/screens/` | Full page screens (home, cart, etc.) |
| `assets/images/` | Product images |

---

## Base Tier — Grading Rubric

| Criteria | Points | Notes |
|----------|--------|-------|
| All 8 core features work correctly | 30 | ~3–4 pts per feature |
| BLoC used correctly for cart state (no `setState` for cart logic) | 20 | Events, states, and bloc wired correctly |
| Correct widget decomposition (`ProductCard`, `CartItemTile`, Dialog as separate widgets) | 15 | No God widgets |
| `Product` and `CartItem` models are well-defined | 10 | Typed fields, no raw Maps |
| Folder structure reflects intent and is consistent | 10 | See required layout above |
| Code is readable (naming, no magic numbers, inline comments where needed) | 10 | Peer-readable standard |
| App runs without crashes on Android emulator or physical device | 5 | Must demo successfully |
| **TOTAL** | **100** | **Pass mark: 70** |

---

## Next Steps

- Attempting the Intermediate tier too? Go to [`03-tier-2-intermediate.md`](03-tier-2-intermediate.md)
- Building with Tier 1 only? Go to [`05-submission-and-grading.md`](05-submission-and-grading.md) once you're done
- Check required packages: [`04-recommended-packages.md`](04-recommended-packages.md)
