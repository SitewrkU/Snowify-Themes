# Snowify Themes

Official and community themes for [Snowify](https://github.com/nyakuoff/Snowify).

## Structure

Each theme lives in its own subdirectory:

```
theme-name/
  theme.css        ← The theme stylesheet
```

## Creating a Theme

1. Create a folder for your theme (e.g. `my-cool-theme/`)
2. Add a `theme.css` file, this is the CSS that overrides Snowify's default variables
3. Start your CSS with a `@name` comment:

```css
/* @name My Cool Theme */

:root {
  --bg-base: #1a1a2e;
  --bg-surface: #16213e;
  --bg-card: #1e2a4a;
  --bg-elevated: #253555;
  --bg-highlight: rgba(100, 150, 255, 0.08);
  --text-primary: #e0e0e0;
  --text-secondary: #a0a0b8;
  --text-subdued: #6a6a80;
  --accent: #64b5f6;
  --accent-dim: rgba(100, 181, 246, 0.12);
  --border-subtle: rgba(255, 255, 255, 0.06);
}
```

### CSS Variables

**Backgrounds**

| Variable | Purpose |
|---|---|
| `--bg-base` | Main background |
| `--bg-surface` | Sidebar, panels |
| `--bg-surface-top` | Top bar / header |
| `--bg-card` | Cards, list items |
| `--bg-elevated` | Hover states, elevated surfaces |
| `--bg-highlight` | Subtle highlights |
| `--bg-gradient-1` | Decorative gradient layer 1 |
| `--bg-gradient-2` | Decorative gradient layer 2 |

**Text**

| Variable | Purpose |
|---|---|
| `--text-primary` | Main text |
| `--text-secondary` | Secondary text |
| `--text-subdued` | Muted text, metadata |

**Accent**

| Variable | Purpose |
|---|---|
| `--accent` | Primary accent color (buttons, links, active states) |
| `--accent-hover` | Accent on hover |
| `--accent-dim` | Low-opacity accent for backgrounds |
| `--accent-dim-hover` | Low-opacity accent on hover |
| `--accent-glow` | Glow/shadow accent |
| `--accent-border` | Accent-tinted borders |

**Surfaces & Shape**

| Variable | Purpose |
|---|---|
| `--glass-border` | Glassmorphism border (e.g. `1px solid rgba(...)`) |
| `--glass-shadow` | Glassmorphism box shadow |
| `--border-subtle` | General subtle borders |
| `--radius` | Border radius for small elements |
| `--radius-lg` | Border radius for cards/panels |

**Going further**

Since themes are injected as a `<style>` tag, you can target any class in Snowify's DOM, add `@keyframes`, use `@font-face`, media queries, custom properties of your own, anything valid CSS supports.

## Submitting a Theme

### Official Themes
Open a PR to this repository with your theme folder.

### Third-Party Themes
1. Create your own GitHub repository with your theme(s)
2. Open a PR to [Snowify's registry](https://github.com/nyakuoff/Snowify/blob/main/plugins/registry.json) to add your theme entry to the `themes` array

#### Registry Entry Format

```json
{
  "id": "my-theme",
  "name": "My Theme",
  "description": "A beautiful custom theme for Snowify.",
  "author": "Your Name",
  "version": "1.0.0",
  "file": "theme.css",
  "preview": ["#1a1a2e", "#64b5f6", "#e0e0e0", "#a0a0b8"],
  "repo": "your-username/your-repo",
  "path": "my-theme",
  "branch": "main",
  "official": false
}
```

- **`preview`** — Array of 4-5 hex colors: `[background, accent, primary-text, secondary-text, ...]`
- **`file`** — CSS filename inside the theme folder (usually `theme.css`)
- **`path`** — Subdirectory in the repo (for monorepos). Omit for single-theme repos.
- **`official`** — Set to `false` for community themes

## License

MIT
