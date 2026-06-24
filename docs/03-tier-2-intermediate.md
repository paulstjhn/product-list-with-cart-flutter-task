# Tier 2 — Intermediate

## Goal

Extend the Base build with responsive layout, polished UX, and a clean separation between the UI and data layers. Intermediate tier targets mentees who want to show real production-readiness thinking.

**All Tier 1 requirements still apply and are still graded.** See [`02-tier-1-base.md`](02-tier-1-base.md) — this document only covers what's *added* on top. Intermediate is Base + everything below, and adds a further **50 points** on top of your Base score.

---

## Additional Requirements

### Responsive Layout

- On wide screens (tablet/desktop or landscape phone ≥ 600px), show a side-by-side layout: product grid on the left, cart panel on the right
- On narrow screens (portrait phone < 600px), stack them: product grid on top, cart accessible via a bottom sheet or floating cart button
- Use `LayoutBuilder` or `MediaQuery` to switch between layouts

### UX Improvements

- Product card image border highlights when that product is in the cart (matching the original design)
- Cart item entry/exit animations — use `AnimatedList` or implicit animations
- "Add to Cart" button on the product card transforms into a quantity stepper once the item is in the cart
- Empty cart state — show a meaningful empty state illustration or message

### Clean Architecture Layer

- Introduce a **Repository** layer between your data source and BLoC
- `ProductRepository` with a `getProducts()` method that returns a `Future<List<Product>>`
- BLoC should depend on the repository, not directly on the raw data
- This makes it easy to swap the data source later (e.g. an API instead of local JSON) without touching the BLoC

### Additional Folder Structure

| Folder | What goes here |
|--------|----------------|
| `lib/repositories/` | `ProductRepository` (abstract + impl) |
| `lib/bloc/product/` | Optional `ProductBloc` for async product loading |

---

## Intermediate Tier — Grading Rubric

Intermediate is scored on top of Base. Your Base score carries over — Intermediate adds a further 50 points.

| Criteria | Points | Notes |
|----------|--------|-------|
| Responsive layout with `LayoutBuilder`/`MediaQuery` | 15 | Both layouts must work |
| Product card image highlights when item is in cart | 5 | Must react to BLoC state |
| Add-to-cart button transitions to quantity stepper | 5 | Driven by cart state, not local widget state |
| Cart item animations (add/remove) | 5 | `AnimatedList` or `AnimatedSwitcher` |
| Empty cart state UI | 5 | Not just white space |
| Repository layer correctly introduced and wired to BLoC | 15 | Abstract class + concrete impl |
| **INTERMEDIATE BONUS TOTAL** | **+50** | **Added to Base score** |

---

## Next Steps

- Check required packages for this tier: [`04-recommended-packages.md`](04-recommended-packages.md)
- Ready to submit? Go to [`05-submission-and-grading.md`](05-submission-and-grading.md)
