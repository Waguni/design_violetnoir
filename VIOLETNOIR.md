# VIOLET NOIR — universal PWA design kit

True-black OLED, glass, electric-violet UI language for progressive web apps.
Companion file: `violetnoir.css` (tokens + primitives). Link it, then follow these rules.

```html
<link rel="stylesheet" href="violetnoir.css">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#050507">
<body class="vn-field">
```

## Non-negotiables

1. **True black only.** Page is `#050507` (OLED black). Panels are translucent (`--vn-glass`) over it. Never a white surface.
2. **One accent.** Violet (`--vn-acc #a855f7`) means active, primary, success. Cyan (`--vn-info #22d3ee`) exists for info status only — never as a second decorative accent.
3. **Glow marks the active element.** High contrast is the identity; glow is reserved for what is selected, focused or live. Max three glowing elements per screen.
4. **Rings, not borders.** `box-shadow: inset 0 0 0 1px …`. No `border: 1px solid`.
5. **44px minimum** tap/click target height, desktop included.
6. **Mono for labels, numbers and code** (`--vn-mono` = JetBrains Mono, uppercase, `0.16em` tracking). Sora for everything else. Never mono for sentences.
7. **Motion: 140–260ms** on `cubic-bezier(.22,1,.36,1)`. No bounce. Infinite loops only for loading.
8. **Radii:** 10 / 14 / 20 / 28 px, pill for anything interactive and inline.

## Token map

| Purpose | Token |
|---|---|
| Page bg | `--vn-bg` `#050507` |
| Elevated panel | `--vn-bg-elev` `#0d0b12` |
| Glass fill | `--vn-glass` / `--vn-glass-2` |
| Hairline | `--vn-line` / `--vn-line-2` |
| Text | `--vn-txt` / `--vn-txt-dim` / `--vn-txt-mute` |
| Accent | `--vn-acc` `--vn-acc-2` `--vn-acc-3` `--vn-acc-ink` |
| Status | `--vn-ok` `--vn-warn` `--vn-danger` `--vn-info` |
| Depth | `--vn-ring` `--vn-shadow` `--vn-shadow-lg` |
| Glow | `--vn-glow-sm` `--vn-glow` `--vn-glow-lg` |
| Spacing | `--vn-s1`…`--vn-s8` (4pt) |
| Motion | `--vn-fast` `--vn-base` `--vn-slow` `--vn-ease` |

## Class vocabulary

`vn-field` (ambient bg) · `vn-grid` (technical grid overlay) · `vn-glass` `vn-card` ·
`vn-btn` + `--primary|--ghost|--quiet|--danger` · `vn-chip` · `vn-input` `vn-select` `vn-textarea` ·
`vn-badge` + `--ok|--warn|--danger|--info|--idle` · `vn-skeleton` ·
`vn-topbar` `vn-bottomnav` `vn-navitem` · `vn-label` `vn-h1` `vn-h2` `vn-num`

## Layout

- **< 900px:** sticky topbar (56px + safe-area-top) + bottom nav (64px + safe-area-bottom). Content scrolls between them.
- **≥ 900px:** 248px sidebar rail + 56px topbar. Content container maxes at 1180px, 24px side padding.
- Fixed bars always add `env(safe-area-inset-*)` padding; the viewport meta must carry `viewport-fit=cover`.

## PWA patterns

- **Install prompt:** own banner, shown from the second session onward. Never on first paint.
- **Offline:** amber pill, `Offline · N changes queued`. Sync success = violet pill with timestamp. Never block the UI.
- **Splash:** manifest `background_color` and `theme_color` both `#050507` so there is no white flash.
- **Push:** ask in context after a relevant action, never on load. Always offer "Not now".
- **Pull-to-refresh:** violet spinner pill sliding in from the top of the scroll container.

## Copy

English, lowercase-technical, factual. Labels are one or two words. No emoji. No exclamation marks except a single CTA. Numbers are tabular mono.
