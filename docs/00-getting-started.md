# Getting Started

This document walks you through everything between "I've just been given this repo link" and "I'm writing my first widget."

There's no API key to register and no `.env` file to manage for this project — all product data is local. That makes setup shorter than usual, but don't skip the asset registration step below; it's the one part that trips people up.

---

## 1. Fork the Repository

Click **Fork** in the top right of this repository on GitHub. This creates your own copy under your account — you'll do all your work there, not on the original.

## 2. Clone Your Fork

```bash
git clone git@github.com:YOUR-USERNAME/flutter-product-list-cart.git
cd flutter-product-list-cart
```

If you haven't set up SSH authentication with GitHub yet, use the HTTPS URL instead, or revisit your Week 3 Git setup notes.

## 3. Initialise Your Flutter Project

This repository currently contains only the brief, its documentation, and an empty `assets/images/` folder — no Flutter project exists yet. You'll create it yourself, inside this same repo, so your forked repository becomes your actual submission.

From the root of the cloned repo:

```bash
flutter create .
```

This generates the standard Flutter project structure (`lib/`, `pubspec.yaml`, `android/`, `ios/`, etc.) without overwriting the documentation files already here.

Confirm everything is wired up correctly:

```bash
flutter doctor
flutter run
```

You should see the default Flutter counter app running. Once that's confirmed working, you're ready to start building against the brief.

## 4. Add Your Dependencies

See [`04-recommended-packages.md`](04-recommended-packages.md) for the required packages. Add them to your `pubspec.yaml` and run:

```bash
flutter pub get
```

## 5. Wire Up the `assets/images/` Folder

The brief requires product images to live in `assets/images/` (see [`02-tier-1-base.md`](02-tier-1-base.md)). This folder already exists in the repo, but Flutter won't bundle it into your app until you declare it in `pubspec.yaml`:

```yaml
flutter:
  uses-material-design: true
  assets:
    - assets/images/
```

Add your product images to that folder, then reference them in your `Product` model's `imageAsset` field (e.g. `assets/images/waffle.jpg`). If you forget this step, your images will exist on disk but throw an asset-not-found error the moment you try to display one — that's almost always what's actually wrong if you hit that error.

## 6. Commit Your Setup

Before writing any feature code, make your first commit so your project history starts clean:

```bash
git add .
git commit -m "chore: initialise flutter project and add dependencies"
git push origin main
```

From here, follow the same Git habits from Week 3: branch per feature, atomic commits, clear messages. Your commit history is part of what gets reviewed.

## 7. Start Building

Head to [`01-overview.md`](01-overview.md) to review the core features, then to [`02-tier-1-base.md`](02-tier-1-base.md) for the full technical requirements and recommended folder structure.

Use [`../CHECKLIST.md`](../CHECKLIST.md) to track your progress as you go.
