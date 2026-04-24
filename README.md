  
`Da je vjecna Crna Gora`

https://dajevjecna.me

# Crna Gora — Montenegro Timeline

An interactive horizontal timeline of Montenegrin history, in four languages (EN / MNE / DE / RU). Everything — layout, styling, and milestone data — lives in a single self-contained file: **`Montenegro Timeline.html`**.

---

## Adding a new milestone

All milestones live in the `EVENTS` array inside `Montenegro Timeline.html`. To add one, drop a new object into that array and refresh the page.

### Minimum template

```js
{
  id: 28,              // unique — just the next number
  year: 2030,          // year the event occurred
  side: "below",       // "above" or "below" — alternate for visual rhythm
  tag: "Modern",       // era — see list below
  key: false,          // true = major turning point (gold ring), false = regular dot
  en: { title: "...", short: "...", desc: "..." },
  me: { title: "...", short: "...", desc: "..." },
  de: { title: "...", short: "...", desc: "..." },
  ru: { title: "...", short: "...", desc: "..." },
},
```

### Optional fields

- **`audio`** — URL to an audio clip that plays when the milestone is opened (see the 2004 National Anthem entry for an example).

### Field reference

| Field | Values |
|---|---|
| `id` | Unique integer. Sequential. |
| `year` | Integer. |
| `side` | `"above"` or `"below"`. |
| `tag` | `"Medieval"`, `"Ottoman Era"`, `"Principality"`, `"Kingdom"`, `"Yugoslavia"`, `"Modern"`. |
| `key` | `true` for major turning points, otherwise `false`. |
| `en` / `me` / `de` / `ru` | Each has `title`, `short`, `desc`. |

---

## Gotchas — read before editing

1. **Keep chronological order.** The rail positions events by their order in the array, not by the `year` field. If you insert out of order, the horizontal layout will look wrong.

2. **All four languages are required.** If you skip `de` or `ru`, that language toggle will render `undefined`. If you don't want to translate, copy the English text into the other slots as a placeholder.

3. **The `tag` must match exactly** (case-sensitive) — `"Modern"`, not `"modern"`; `"Ottoman Era"` with the space. Otherwise the era color and era-jump chip won't apply.

4. **`side` alternates for rhythm.** It doesn't have to strictly alternate, but check the adjacent entries so cards don't stack on top of each other visually.

5. **`key: true` adds a gold ring** around the dot — use it sparingly (roughly one per era) so the real turning points stand out.

6. **Commas matter.** Each event object ends with a comma. Missing one will break the whole page with a silent JS parse error.

---

## Editing existing milestones

Same file, same `EVENTS` array — find the entry by `id` or `year` and edit in place. Refresh the page to see changes.

## Removing a milestone

Delete the whole object from the array. You don't need to renumber the remaining `id`s (they just need to stay unique), but renumbering keeps things tidy.

---

## Running locally

Open `Montenegro Timeline.html` directly in a browser — no build step, no server needed. It works from `file://`.

## Hosting on GitHub Pages

Just commit the file and enable Pages. That's it. No build configuration required.

