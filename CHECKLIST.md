# Project Checklist

Tick these off as you go. This mirrors the grading rubrics in [`docs/02-tier-1-base.md`](docs/02-tier-1-base.md) and [`docs/03-tier-2-intermediate.md`](docs/03-tier-2-intermediate.md) — use it as a running progress tracker, not just a pre-submission review.

---

## Setup

- [ ] Forked the brief repository
- [ ] Cloned my fork locally
- [ ] Ran `flutter create .` to initialise the project inside this repo
- [ ] Added required dependencies (`flutter_bloc`, `equatable`) to `pubspec.yaml` and ran `flutter pub get`
- [ ] Declared `assets/images/` in `pubspec.yaml` and confirmed an image renders correctly
- [ ] Made my first commit

---

## Core Features (Required at Every Tier)

- [ ] Browse a product list loaded from a local JSON/mock data source
- [ ] Add a product to the cart with a single tap
- [ ] View the cart panel showing all added items
- [ ] Increase or decrease quantity for each cart item
- [ ] Remove an item from the cart
- [ ] See a running order total that updates in real time
- [ ] Tap "Confirm Order" to open a confirmation modal/dialog
- [ ] Tap "Start New Order" inside the modal to reset the cart and return

---

## Tier 1 — Base Architecture

**State Management**
- [ ] `flutter_bloc` used for all cart state
- [ ] `CartBloc` handles: `AddToCart`, `RemoveFromCart`, `IncrementQuantity`, `DecrementQuantity`, `ResetCart`
- [ ] `CartState` exposes: list of cart items, item count, order total
- [ ] No `setState` used for any cart logic

**Data**
- [ ] Product data comes from a local source (hardcoded list, JSON asset, or Dart model file)
- [ ] `Product` model defined (`id`, `name`, `category`, `price`, `imageAsset`)
- [ ] `CartItem` model defined (`product`, `quantity`)
- [ ] No raw `Map`s passed between layers — typed models used throughout

**Widget Structure**
- [ ] `ProductCard` widget built
- [ ] `CartItemTile` widget built
- [ ] `OrderConfirmationDialog` built and shown via `showDialog`
- [ ] No business logic inside any widget `build` method

**Folder Structure**
- [ ] `lib/models/`
- [ ] `lib/bloc/`
- [ ] `lib/data/`
- [ ] `lib/widgets/`
- [ ] `lib/screens/`
- [ ] `assets/images/`

**Code Quality**
- [ ] Naming is clear and consistent
- [ ] No magic numbers — meaningful constants/names used
- [ ] Inline comments explain non-obvious logic
- [ ] App runs without crashing on an Android emulator or physical device

---

## Tier 2 — Intermediate (Optional, +50 points)

**Responsive Layout**
- [ ] Side-by-side layout (product grid + cart panel) on wide screens (≥ 600px)
- [ ] Stacked layout (grid on top, cart via bottom sheet or floating button) on narrow screens (< 600px)
- [ ] `LayoutBuilder` or `MediaQuery` used to switch between layouts

**UX Improvements**
- [ ] Product card image border highlights when that product is in the cart
- [ ] Cart item entry/exit animations (`AnimatedList` or implicit animations)
- [ ] "Add to Cart" button transforms into a quantity stepper once the item is in the cart
- [ ] Empty cart state shows a meaningful message or illustration — not blank space

**Clean Architecture Layer**
- [ ] `ProductRepository` introduced between data source and BLoC (abstract + impl)
- [ ] `ProductRepository.getProducts()` returns `Future<List<Product>>`
- [ ] BLoC depends on the repository, not directly on the raw data source
- [ ] (Optional) `ProductBloc` added for async product loading

**Additional Folder Structure**
- [ ] `lib/repositories/`
- [ ] `lib/bloc/product/` (if using a separate `ProductBloc`)

---

## Ground Rules — Final Check

- [ ] The original JS project was referenced for feature behaviour only, not copied for logic
- [ ] `flutter_bloc` is the only state management approach used for cart state (no GetX, Provider, or Riverpod)
- [ ] No external UI kits used — all widgets built from scratch
- [ ] I can explain every line of any AI-assisted code in my verbal walkthrough
- [ ] I have a specific decision picked out and ready to explain in my walkthrough

---

## Submission

- [ ] GitHub repository link ready to share
- [ ] `README.md` updated with: tier attempted, how to run the project, known issues
- [ ] Demo recording made, or APK built and tested
- [ ] Confirmed the project runs from a clean clone (not just on my own machine)
- [ ] Tested edge cases myself: empty cart, rapid repeated taps, quantity boundaries
