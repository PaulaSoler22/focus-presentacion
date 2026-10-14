# Plantilla Maestra — Presentaciones de Simuladores CompanyGame

> **Esta carpeta es una PLANTILLA.** Para una presentación nueva, cópiala completa,
> renómbrala (p. ej. `businessglobal-presentacion/`) y rellena los slides variables.
> Distribuidor: **Simuladores de Negocios Colombia** (Grupo Edutec).

## Cómo se construye una presentación nueva

1. **Copiar** esta carpeta y renombrarla con el nombre del simulador.
2. Decirle a Claude: *"Esta presentación es para el simulador **[NOMBRE]**"* y darle la
   información del simulador (manual, capturas, datos).
3. Claude **reemplaza los tokens `[[...]]`** y **rellena los slides variables**, conservando
   los slides fijos tal cual.
4. Guardar las imágenes específicas en `assets/` (ver **Convenciones de imágenes** abajo).

## Convenciones de imágenes (estándar Corbatul — la presentación más pulida)

- **Formato y nombre descriptivo**: las capturas van en **`.jpg`** (pesan menos que PNG) con
  nombre que dice qué son, no numerado. Ej. Cuadro de Mando → `cm-valor.jpg`, `cm-marketing.jpg`,
  `cm-produccion.jpg`; Decisiones → `dec-capital.jpg`, `dec-ventas.jpg`, `dec-produccion.jpg`.
  (El logo, cartelera y avatares conservan su formato original.)
- **Siempre clicables (lightbox)**: cada `<img>` de captura lleva
  `onclick="openLightbox('assets/x.jpg','Título descriptivo')"` y `loading="lazy"`.
- **Tamaño / encuadre**:
  - Cuadro de Mando (`.cm-img img`): ocupa el 100 % del ancho de su tarjeta; no fijar alto.
  - Decisiones (`.dec-shot img`): 100 % de ancho con tope `max-width:920px` (centrada).
  - El lightbox muestra la imagen a `max-height:86vh` — no recortar capturas, se ven completas.
- **Organización del Cuadro de Mando**: usar **siempre `.cm-grid`** (grid fijo de 3 columnas),
  igual que FoodCompany — **no uses `.cm-masonry`**, aunque las capturas tengan alturas distintas
  (se dejó de usar para que todas las presentaciones se vean iguales). Cada tarjeta `.cm-card` lleva
  `.cm-img` + `.cm-body` con `.cm-titlerow` (h3 + `.cm-badge`) + `.cm-desc` + bloque **«Por qué
  analizarlo»** (`.cm-why-label` + `.cm-why-text`).
- **Decisiones del Simulador — componente distinto al de Cuadro de Mando**: usa **siempre
  `.dec-block`** (franja `.dec-head` con `.dec-num` numerado + `.dec-shot` con la captura completa
  debajo), **nunca** `.cm-card`/`.cm-grid` para esta sección — aunque ambos componentes compartan
  familia visual, Decisiones NO es una galería de tarjetas en grid.

## Tokens a reemplazar (búscalos con `[[`)

| Token | Qué es | Ejemplo (FoodCompany) |
|-------|--------|------------------------|
| `[[SIMULADOR]]` | Nombre del simulador | FoodCompany |
| `[[SUBTITULO]]` | Subtítulo de portada | Simulador de Gestión de una Empresa del Sector Lácteo |
| `[[PARRAFO_CONTEXTO]]` | 2-3 frases de qué es | … dirige una compañía láctea … |
| `[[NIVEL]]` | Nivel / dificultad | Nivel 4 · Estratégico |
| `[[DURACION]]` | Duración | 16–32 horas |
| `[[LINEAS_PRODUCTO]]` | Badge de líneas/foco | 🥛🥣🧀 3 Líneas de Producto |
| `[[AREA_CONOCIMIENTO]]` | Área CompanyGame | Marketing y Ventas |
| `[[EMOJI]]` | Emoji de marca (cierre) | 🥛 |
| `[[SUBTITULO_*]]`, `[[TITULO_*]]`, `[[FACTORES_VALOR]]` | Títulos/subtítulos de slides variables | — |

## Estructura: 18 slides (NO cambiar la cantidad sin actualizar el contador del nav)

| # | Slide | Tipo | Notas |
|---|-------|------|-------|
| 1 | Portada + Contexto | **FIJO** (estructura) | Branding CompanyGame; cambia solo nombre/imagen vía tokens |
| 2 | Cartelera de Simuladores | **FIJO** | Usa `assets/cartelera.jpg` y `assets/avatares.png` (portafolio CompanyGame) |
| 3 | Ingreso a la Plataforma | **FIJO** | URL `plataforma.companygame.net`; idéntico en todas |
| 4 | Divisoria — Entorno de Simulación | **FIJO** | `.section-divider`; separa "acceso" de "contenido del simulador" |
| 5 | Manual del Simulador | **FIJO** (portada/link pendientes) | Portada `assets/manual-cover.png` + botón de descarga; llega con placeholders `.reserved` hasta que se suba el manual real |
| 6 | ¿Qué es? | variable | Tarjetas `.card-grid cols4` |
| 7 | Cadena de Valor | variable | `.value-chain` + `.card-grid` |
| 8 | Producción / Insumos | variable | `.data-table` + tarjetas |
| 9 | Áreas de Decisión | variable | `.card-grid` |
| 10 | Segmentos | variable | `.two-col` + `.seg-row` — **sin factores de competitividad**, esa sección se eliminó |
| 11 | Valor de la Compañía | variable | `.factor-accordion` con % — va **antes** de Cuadro de Mando, no después |
| 12 | Divisoria — Cuadro de Mando | **FIJO** | `.section-divider` |
| 13 | Cuadro de Mando | variable | `.cm-grid` + `.cm-card` (siempre, nunca `.cm-masonry`) · capturas `assets/cm-<nombre>.jpg` |
| 14 | Divisoria — Decisiones del Simulador | **FIJO** | `.section-divider` |
| 15 | Decisiones del Simulador | variable | `.dec-block` · capturas `assets/dec-<nombre>.jpg` |
| 16 | Métodos de Implementación | **FIJO** | Genérico (deductivo/inductivo/mixto/alternos) |
| 17 | Preguntas Frecuentes | variable (semi) | Preguntas reutilizables; ajustar respuestas del simulador |
| 18 | Cierre / Gracias | **FIJO** | Contacto del distribuidor (email + WhatsApp + logo SDN) + redes sociales (LinkedIn/YouTube/Web) |

Cada slide variable trae un `<div class="reserved">` con instrucciones y un comentario
`<!-- VARIABLE · ... -->` que indica el componente recomendado.

### Segmentos (slide 10) — ya NO lleva competitividad

La antigua sección "Segmentos y Competitividad" se simplificó a solo **Segmentos**: segmentos
de demanda + canales de distribución. El acordeón de factores de competitividad (Precio/Marca/
Producto/Cobertura por segmento) se eliminó de esta familia de presentaciones — no lo agregues
en presentaciones nuevas ni lo reincorpores en las existentes.

### Cuadro de Mando (slide 13) y Decisiones (slide 15) — mismo estilo visual en todas

Ambas slides comparten familia visual (tarjetas blancas con sombra, imagen arriba, degradado
`--primary`/`--amber`) pero son **componentes distintos** — no los confundas:
- **Cuadro de Mando**: `.cm-grid` (3 columnas fijas) de `.cm-card` — cada una con `.cm-img`,
  `.cm-body` → `.cm-titlerow` (h3 + `.cm-badge` de categoría) → `.cm-desc` → `.cm-why-label` +
  `.cm-why-text` ("Por qué analizarlo").
- **Decisiones del Simulador**: lista vertical de `.dec-block` — cada uno con `.dec-head`
  (`.dec-num` numerado + h3 + p) y `.dec-shot` (la captura completa, ancho completo, sin badge
  ni "por qué importa" separado — si hay ese dato, va fusionado en el mismo párrafo de `.dec-head`).

### Valor de la Compañía (slide 11) — estructura fija de acordeón

Usa **siempre** el mismo componente que FoodCompany: `<div class="factor-accordion">` con un
`<div class="factor-item">` desplegable por factor (variantes `factor-orange/amber/green/teal/
purple/red/blue`), cada uno con `.factor-tag` (el %) y, al desplegar, `Descripción` / `¿Qué
evalúa?` / `.factor-consejo`. Solo cambian los factores, los % y el texto — no el componente.
Esta slide va **antes** de la divisoria de Cuadro de Mando, no después.

### Slides divisorias (`.section-divider`)

Marcan el inicio de un bloque grande de contenido (fondo degradado `--primary → --amber`,
ícono grande animado, texto corto). Estructura mínima:

```html
<div class="slide" id="slideN">
    <div class="section-divider">
        <div class="sd-icon">🖥️</div>
        <div class="sd-eyebrow">Sección</div>
        <h1>Título de la sección</h1>
        <p>Frase corta de contexto</p>
        <div class="sd-rule"></div>
    </div>
</div>
```

No llevan `.slide-header` ni `.slide-number`. Usan el mismo degradado de la plantilla
(`var(--primary)`/`var(--amber)`) — al cambiar la paleta por simulador, se adaptan solas.

## Componentes de estilo disponibles (ya en el CSS)

- **Tarjetas**: `.card-grid` / `.card-grid.cols4` + `.card` (variantes `bd-amber/green/teal/purple/red`)
- **Tabla**: `.data-table`
- **Flujo**: `.value-chain` + `.chain-box` (`cb-amber/green/teal`)
- **Acordeón de factores**: `.factor-accordion` + `.factor-item` (`factor-orange/amber/green/teal/purple/red/blue`)
- **Galería de informes**: `.cm-grid` + `.cm-card` (siempre — `.cm-masonry` ya no se usa)
- **Bloques de decisión**: `.dec-block` (con `.dec-num`)
- **Acordeón FAQ**: `.accordion` + `.accordion-item`
- **Dos columnas**: `.two-col` · **Segmentos**: `.seg-row` · **Badges**: `.badge` (`badge-orange/green/teal/amber/purple`)
- **Lightbox** de imágenes: `onclick="openLightbox('assets/x.jpg','Título')"` + `loading="lazy"`

## Paleta (identidad CompanyGame/FoodCompany — ajustable por simulador)

```
--primary:#F58220  --primary-dark:#E06D10  --amber:#F9A825
--accent-green:#7BC143  --accent-teal:#00B4D8  --accent-purple:#9B59B6
--cg-blue:#1A5276
```
Si el simulador tiene identidad propia, cambia estas variables en `:root`.

## Datos fijos del distribuidor (no cambian entre simuladores)

- Plataforma de acceso: **https://plataforma.companygame.net/**
- Email: **fidelizacion@simuladoresdenegocios.co**
- WhatsApp: **301 790 3086** (`https://wa.me/573017903086`)
- Logo distribuidor: `assets/logo-sdn.png`
- Redes sociales (slide de Cierre, `.social-row` con `.social-icon`):
  - LinkedIn: `https://co.linkedin.com/company/simuladores-de-negocios-colombia-sas`
  - YouTube: `https://www.youtube.com/@SimuladoresdeNegocios/videos`
  - Página web: `https://simuladordenegocios.co/`

## Tecnología

HTML5 + CSS3 + JS vanilla, todo embebido en `index.html`. Sin frameworks. Navegación por
flechas/teclado/swipe ya implementada. No tocar el `<script>` salvo que cambie el nº de slides.
