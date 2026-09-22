# Maximus Haven — website

Static one-page site for **Maximus Haven restaurante & cafetería**, a family-run
Filipino restaurant in Tetuán, Madrid.

- **Live:** <https://maximus-haven.github.io>
- **Address:** C/ Marqués de Cortina 2, 28020 Madrid
- **Phone:** 602 586 955 · 910 42 62 68

## Stack

None. It's one HTML file plus images — no build step, no dependencies, no
framework. Open `index.html` in a browser and you're looking at production.

| File | Purpose |
|---|---|
| `index.html` | The entire site: markup, CSS and JS inline. |
| `img/` | Dish photography (lomi, sisig, halo-halo, lechon kawali). |
| `favicon.svg`, `apple-touch-icon.png` | Browser tab and iOS home-screen icon. |
| `robots.txt`, `sitemap.xml` | Search engine basics. |
| `.nojekyll` | Tells GitHub Pages to skip Jekyll processing. |

## Deploying

GitHub Pages serves `main` from the repository root. Push to `main` and the site
redeploys within a minute or two — there is nothing to build.

```bash
git push
```

## Editing

Everything lives in `index.html`. Search for the text you want to change.

**Opening hours** appear in three places: the red hours strip, the
`openingHoursSpecification` block in the JSON-LD (which is what Google reads),
and the `I18N` object at the bottom for the English and Filipino translations.
Change all three or they'll disagree.

**Dishes** are `<article class="chapter">` blocks. Each one sets its own accent
colour via the inline `--accent` custom property. Translations for the copy live
in the `I18N` object.

**Photos** — replace the file in `img/` keeping the same filename. JPEG, max
1400px on the long edge, under ~400KB. The hero and the chapters reference them
by relative path.

**Contact details** — search for `602 586 955` or `Marqués de Cortina`. Note
they also appear in the JSON-LD block, which needs updating too.

### Absolute URLs

The Open Graph tags, canonical link, JSON-LD and `sitemap.xml` all hardcode
`https://maximus-haven.github.io`. If the site ever moves to a custom domain,
find and replace that string across `index.html`, `sitemap.xml` and `robots.txt`
— otherwise link previews will point at the old host.

## Browser support

Scroll-driven animations use CSS scroll timelines (`animation-timeline`), which
work in recent Chrome, Edge and Safari. Firefox and older browsers render the
same page laid out normally, without the motion — it degrades rather than
breaks. `prefers-reduced-motion` is respected throughout.

Fonts (Fraunces, Manrope) load from Google Fonts, so the first paint needs a
network connection.

## Features

- Three languages — Spanish (default), English, Filipino — switched client-side,
  stored in `localStorage`.
- Light and dark theme toggle, defaulting to light regardless of OS setting.
- Structured data marking the business up as a `Restaurant` for Google.

---

## Para la familia / Para sa pamilya

Para cambiar algo sencillo en la web, abre `index.html` y busca el texto:

- **El horario** → busca `18:00`. Aparece tres veces en el archivo; cámbialo en
  todas.
- **El teléfono** → busca `602 586 955`.
- **Una foto** → sustituye el archivo dentro de `img/` con el mismo nombre.
- **Un plato** → busca el nombre del plato (`Lomi`, `Sisig Max`…).

Después de guardar los cambios, la web se actualiza sola en uno o dos minutos.
