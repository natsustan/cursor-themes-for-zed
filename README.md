# Cursor Theme Pack for Zed

An unofficial all-in-one Cursor theme extension for Zed. One installation
provides the complete theme family:

- Cursor Dark
- Cursor Dark Midnight
- Cursor Dark High Contrast
- Cursor Light

## Why Cursor Theme Pack?

The Zed extension registry already contains individual Cursor-inspired themes,
but none of them provides all four variants as one consistently generated
package. Cursor Theme Pack is intended for users who want the complete family
from one extension, including Light and High Contrast, rather than installing
and mixing multiple theme extensions.

This community project is not affiliated with or endorsed by Anysphere. Cursor
is a product and trademark of Anysphere, Inc.

## Installation

After the extension is published:

1. Open Zed's Extensions page.
2. Search for `Cursor Theme Pack` and install it.
3. Run `theme selector: toggle` and choose a Cursor theme.

For local development, run `zed: install dev extension` and select this
repository root.

## Previews

| Cursor Dark | Cursor Dark Midnight |
| --- | --- |
| ![Cursor Dark](preview/cursor-dark-preview.png) | ![Cursor Dark Midnight](preview/cursor-dark-midnight-preview.png) |

| Cursor Dark High Contrast | Cursor Light |
| --- | --- |
| ![Cursor Dark High Contrast](preview/cursor-dark-high-contrast-preview.png) | ![Cursor Light](preview/cursor-light-preview.png) |

## Development

The checked-in Zed theme files are generated from the corresponding VS Code
theme sources:

```sh
bun install
bun run generate
bun run check
```

`bun run check` verifies without modifying files and fails if the checked-in
themes are missing, stale, or unexpected.

## Publishing to the Zed extension registry

The extension ID is `cursor-theme-pack`. In a fork of
[`zed-industries/extensions`](https://github.com/zed-industries/extensions),
add this repository at the matching submodule path:

```sh
git submodule add https://github.com/nexmoe/cursor-themes-for-zed.git extensions/cursor-theme-pack
```

Add the matching registry entry to `extensions.toml`:

```toml
[cursor-theme-pack]
submodule = "extensions/cursor-theme-pack"
version = "2.0.0"
```

Then run the required formatter before opening the pull request:

```sh
pnpm sort-extensions
```

The pull request should explain that this extension's distinct purpose is to
provide the complete four-theme Cursor family in one package. The submodule
must point to a commit reachable from this repository's default branch, and
the registry version must match `extension.toml`.

## Project layout

```text
extension.toml
themes/*.json
vscode-themes/*.json
scripts/convert-vscode-to-zed.mjs
preview/*.png
```

The MIT license covers this project's conversion code and generated Zed theme
files. The Cursor name and original visual design remain the property of their
respective owner.
