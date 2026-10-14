# 🚀 Cómo crear una presentación nueva (paso a paso)

Esta carpeta es tu **plantilla maestra**. Tiene los slides fijos ya hechos y los variables
como huecos. Para cada simulador nuevo solo repites estos pasos:

## 1. Copia la carpeta
Copia toda la carpeta `plantilla-presentacion` y renómbrala con el nombre del simulador.
Ejemplo: `businessglobal-presentacion`.

> 💡 También puedes pedírselo a Claude: *"Copia la plantilla maestra para una presentación de BusinessGlobal"*.

## 2. Abre la nueva carpeta en VS Code y abre el chat de Claude

## 3. Dile a Claude qué simulador es y dale la información
Ejemplo de mensaje inicial:

> *"Esta presentación es para el simulador **BusinessGlobal**. Es un simulador de nivel 5
> de estrategia global. Aquí está la info del manual: [pegas o adjuntas]. Rellena los slides
> variables y reemplaza los tokens."*

Claude ya sabe (por el `CLAUDE.md` de la carpeta) cuáles slides son fijos, cuáles variables,
qué tokens reemplazar y qué componentes de estilo usar.

## 4. Sube las imágenes a `assets/`
- `portada.png` → imagen alusiva del simulador (portada e intro)
- `cm-01.png`, `cm-02.png`… → capturas del Cuadro de Mando (slide 9)
- `dec-01.png`, `dec-02.png`… → capturas de las pantallas de decisión (slide 10)

Los 3 archivos que **ya vienen** (`cartelera.jpg`, `avatares.png`, `logo-sdn.png`) sirven para
cualquier simulador CompanyGame — normalmente no los cambias.

## 5. Revisa en el navegador
Abre `index.html`. Los slides fijos (1, 2, 3, 12, 14) ya están listos; revisa los variables.

---

### ¿Qué es fijo y qué es variable?
- **Fijos** (no los rehaces): Portada, Cartelera, Ingreso a Plataforma, Métodos de Implementación, Cierre.
- **Variables** (los rellenas según el simulador): ¿Qué es?, Cadena de Valor, Producción,
  Áreas de Decisión, Segmentos, Cuadro de Mando, Decisiones, Valor de la Compañía, FAQ.

### Detalle técnico
Todo el detalle (tokens, componentes, paleta, datos del distribuidor) está en `CLAUDE.md`.
