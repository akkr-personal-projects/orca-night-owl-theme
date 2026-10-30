# Night Owl for Orca (unofficial)

An unofficial Night Owl-inspired theme for Orca, with app colors, editor syntax colors, and a matching terminal palette. Based on the color scheme by Sarah Drasner. Not affiliated with Stably or the original author.

## Repository creation

Create a public GitHub repository named `orca-night-owl-theme`, with **no starter README, .gitignore or license**. Extract the ZIP and put the contents of its `orca-night-owl-theme/` directory at the repository root.

Edit `orca-plugin.json`:
- Replace `your-github-name` in `publisher` with your exact GitHub username (lowercase slug). It must match the repository owner.
- Replace `your-github-name` in `repository` with the same username.
- Do not rename `id` to a string starting with `orca-`: reserved for official plugins.

## Test locally first (no catalog needed)

1. Use Orca >=1.4.245.
2. Orca **Settings -> Plugins -> Turn on plugins**.
3. Choose **Development folders...** and select the **orca-night-owl-theme** directory (with `orca-plugin.json` directly inside).
4. Review and enable the plugin.
5. In Orca appearance settings, select Night Owl for the **dark app theme**. Under Terminal settings, select **Night Owl** for the terminal theme. Code colors come from the app theme.
6. Save edits to the theme JSON; Orca's development folder watcher reloads theme edits.

For formal validation, clone the Orca source repository, install its dependencies per the official author guide, then run `pnpm validate:plugin /path/to/orca-night-owl-theme` from the Orca source checkout.

## Push to GitHub

From inside the extracted `orca-night-owl-theme` directory:

```bash
git init
git add .
git commit -m "Add Night Owl theme for Orca"
git branch -M main
git remote add origin https://github.com/YOUR_GITHUB_NAME/orca-night-owl-theme.git
git push -u origin main
```

Replace `YOUR_GITHUB_NAME` before running. Your Git credential setup must support GitHub authentication.

## Publishing for installation via the catalog

Orca plugin catalogs have an `orca-catalog.json` with releases pinned to a commit and content hash. **A plugin repository alone is not yet a catalog.** The official validator generates the release data; do not guess the hash. See:

- https://github.com/stablyai/orca/blob/main/docs/reference/plugin-authoring.md
- https://github.com/stablyai/orca/blob/main/docs/reference/plugin-catalog.md

You can create a separate catalog repository or add the plugin to a community catalog after validation. To use it on your own desktop, **Development folders** is the simpler path.

## Files
- `orca-plugin.json`: Manifest v2, data-only plugin (no runtime code or permissions)
- `themes/night-owl.json`: Dark app theme and code tokenColors
- `terminal/night-owl.json`: Terminal colors
- `LICENSE`: Original Night Owl MIT copyright notice

## Origins

Original Night Owl: https://github.com/sdras/night-owl-vscode-theme (MIT). The colors here are a hand-adapted approximation, not a complete VS Code engine or semantic-token port. Orca has its own token selection and contrast rules, so some text colors may differ.
