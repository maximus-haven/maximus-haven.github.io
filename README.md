# Maximus Haven — sitio web

Web de **Maximus Haven restaurante & cafetería**
C/ Marqués de Cortina 2, 28020 Madrid · Tetuán

Publicado en <https://maximus-haven.github.io>

## Qué hay aquí

| Archivo | Para qué sirve |
|---|---|
| `index.html` | **Toda la web**: textos, estilos y animaciones en un solo archivo. |
| `img/` | Las fotos de los platos (lomi, sisig, halo-halo, lechón kawali). |
| `favicon.svg`, `apple-touch-icon.png` | El icono que sale en la pestaña del navegador y en el móvil. |
| `robots.txt`, `sitemap.xml` | Para que Google encuentre la web. |

## Cómo cambiar cosas

**El horario** — busca `HORARIO` o `18:00` en `index.html`. Está tres veces:
una en la barra de horario, otra en los datos de Google (`openingHoursSpecification`)
y las traducciones en inglés y filipino al final del archivo.

**Un plato o su descripción** — busca el nombre del plato (`Lomi`, `Sisig Max`…).
Cada plato es un bloque `<article class="chapter">`.
Las traducciones están abajo del todo, en `const I18N`.

**Una foto** — sustituye el archivo dentro de `img/` manteniendo el mismo nombre.
Recomendado: JPG, máximo 1400 px de ancho, menos de 400 KB.

**El teléfono o la dirección** — busca `602 586 955` o `Marqués de Cortina`.

Después de cualquier cambio, GitHub vuelve a publicar la web sola en 1–2 minutos.

## Idiomas

Español (por defecto), English y Filipino — botón ES / EN / FIL arriba a la derecha.
Tema claro y oscuro con el botón de sol/luna.

## Notas técnicas

- Sitio estático, sin dependencias ni proceso de build.
- Las tipografías vienen de Google Fonts.
- Las animaciones de scroll usan CSS scroll timelines: funcionan en Chrome,
  Edge y Safari recientes; en el resto la web se ve igual, sin movimiento.
- Respeta `prefers-reduced-motion`.
