# TecnoCana — Sitio HTML5

Sitio de tres páginas para **TecnoCana**, una tienda ficticia de computadoras
en Bávaro, Punta Cana: venta de laptops y PCs, taller de reparación y soporte
a negocios de la zona.

- **Sitio publicado:** https://luismartin023.github.io/tecnocana/
- **Autor:** Luis Martin Peña Mejia · Matrícula **2023-4341**
- **Curso:** ISW-311-050 Tecnologías de Internet I · Sept–Dic 2026

## Estructura

| Página | Contenido |
|---|---|
| `index.html` | Portada: quiénes somos, qué ofrecemos, noticia con cita, aside con `details` |
| `servicios.html` | Listas (ul anidada, ol `reversed`, dl), tabla de precios, `figure`, `iframe`, `audio`, `pre` |
| `contacto.html` | Formulario completo con validación nativa y los cinco tipos de enlace |
| `img/` | `logo.svg` y `local.svg` (ilustraciones propias en SVG) |
| `media/` | `bienvenida.wav` (audio de saludo de la tienda) |
| `docs/` | `catalogo-tecnocana.pdf` (lista de precios descargable) |

## Mapa de etiquetas — las nueve familias

| Familia | Dónde se usó | Por qué esa etiqueta |
|---|---|---|
| **1. Cimientos del documento** (`doctype`, `html`, `head`, `body`, `meta`, `title`) | Las 3 páginas: `lang="es"`, `charset=UTF-8`, `viewport`, `title` y `meta description` distintos en cada una | Son el esqueleto mínimo de todo documento HTML5; el `title` y la `description` propios de cada página mejoran accesibilidad y resultados de búsqueda |
| **2. Semántica estructural** (`header`, `nav`, `main`, `section`, `article`, `aside`, `footer`) | `header`/`nav`/`main`/`footer` en las 3 páginas; 2 `section` con `h2` en index; `article` para la noticia de la jornada de diagnóstico; `aside` para el "Dato rápido" en index y "Escúchanos" en servicios | `article` porque la noticia tiene sentido por sí sola si se extrae; `aside` porque el dato del SSD complementa pero no interrumpe el contenido principal; `section` agrupa bloques temáticos con su propio encabezado |
| **3. Encabezados** (`h1`–`h3`) | Un solo `h1` por página (nombre del sitio/tema); `h2` en cada `section`/`article`/`aside` | Jerarquía sin saltos: h1 → h2; un solo h1 por página como manda la práctica |
| **4. Texto en línea** (`p`, `strong`, `em`, `mark`, `del`, `ins`, `abbr`, `small`, `sub/sup`, `code`, `kbd`, `pre`) | `strong` para lo importante (laptop, garantías), `em` para énfasis de tono, `mark` para la garantía de 90 días, `del`/`ins` para el descuento que subió de 10% a 15%, `abbr`+`title` para SSD/RAM/UCE/LAN, `small` para horario y copyright, `code` para el error `INACCESSIBLE_BOOT_DEVICE`, `kbd` para las teclas Windows+Pausa y Tab, `pre` para la orden de servicio con formato fijo | Cada una aporta significado distinto: `del`/`ins` muestran una corrección real de precio, `kbd` marca entrada de teclado, `code` marca un literal de sistema, `pre` conserva los espacios del formato ASCII |
| **5. Citas** (`blockquote`+`cite`, `q`) | `blockquote` en la noticia del index con `cite` a la fuente; `q` para el lema de la tienda | `blockquote` para la cita en bloque con fuente, `q` para la cita corta dentro del párrafo |
| **6. Listas** (`ul`, `ol`, `dl`) | `ul` con sublista anidada dentro del `li` en servicios (Reparación → pantallas, teclados…); `ol reversed` para el top 5 de accesorios en cuenta regresiva; `dl` para el glosario (SSD, RAM, GPU, PSU, BIOS) | La sublista modela la jerarquía real servicio→subtareas; `reversed` da la cuenta 5→1 de un ranking; `dl` es la etiqueta correcta para pares término/definición |
| **7. Enlaces** (`a`) | Nav igual en las 3 páginas; externo `target="_blank" rel="noopener"` a intel.la en contacto; `mailto:` y `tel:` en contacto y footer; interno `#precios`/`#mapa`/`#directo`; `download` para el catálogo PDF | `noopener` evita que la página externa controle la nuestra; `mailto`/`tel` abren la app correcta; `download` fuerza descarga del PDF |
| **8. Multimedia** (`img`, `figure`, `figcaption`, `iframe`, `audio`, `source`) | `img` para logo y fachada (SVG propios) con `alt` que describe lo que se ve; `figure`+`figcaption` para la fachada en servicios; `iframe`+`title` con el mapa de OpenStreetMap; `audio controls`+`source` con el saludo de la tienda | `figure`/`figcaption` une imagen con su leyenda; `title` en el iframe lo hace accesible a lectores de pantalla; `controls` da reproducción nativa sin scripts |
| **9. Tablas** (`table`, `caption`, `thead`, `tbody`, `tfoot`, `tr`, `th`, `td`, `colspan`, `rowspan`) | Tabla de precios en servicios: `caption`, `th scope="col"` en el encabezado, `th scope="rowgroup"` con `rowspan` para agrupar Mantenimiento y Reparación, 6 filas en `tbody`, `tfoot` con `colspan` para las notas | `scope` y `rowgroup` le dicen al lector de pantalla qué encabezado cubre cada celda; `colspan`/`rowspan` combinan celdas donde los datos comparten categoría o nota |
| **+ Formularios** (`form`, `fieldset`, `legend`, `label`, `input`, `select`, `optgroup`, `textarea`, `button`) | Formulario de contacto: 2 `fieldset` con `legend` (datos / solicitud), 10 tipos de `input` (text, email, tel, url, date, number, range, color, checkbox, radio), `select` con 3 `optgroup` (Taller/Ventas/Negocios), `textarea`, `button` | `fieldset`+`legend` agrupa campos relacionados; cada `input` usa el tipo que valida nativamente (`email`, `tel` con `pattern`, `number` con `min`/`max`); `label for`+`id` asocia cada etiqueta a su campo |
| **+ Interactivas** (`details`, `summary`) | Dos `details` en el aside de index (preguntas frecuentes) | Despliega respuestas sin JavaScript, con `summary` como título clicable |

## Validación

Las tres páginas pasan `validator.w3.org` sin errores.

## Cómo verlo localmente

Abrir `index.html` en el navegador, o servir la carpeta:

```
python -m http.server 8080
```
