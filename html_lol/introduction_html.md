# Proceso de investigacion teorica de HTML

> **Obgetivos:** Investigar los fundamentos de HTML de forma progresiva, para sentar las bases para maquetar documentos web accesibles, semanticos y optimizados.

---

## introducción y contexto histórico

HTML nace en 1991 de la mano de Tim Berners-Lee como un formato sencillo para compartir documentos cientofocos en la web. su progreso de evolucion a sido progresovo atraves de **HTML 2.0, 3.2, 4.01 (Transitional/Strict)** y llego a **XHTML 1.0/1.1** (versión basada en XML). en 2014 se estabdariza **HTML5**, hoy es desarrollo permanente por el **WHATWG** (living standar). Al comprender la evolucion explica porque existe **quiks mode**, atributos obsoletos y mejores practicas modernas.

## HTML en la industria web: *relebancia actual*

### Importancia fundamental

HTML sigue siendo la **piedra angular**  del desarrollo web:
- **100% de sitios web** lo utilizan como base (W3Techs)
- **Havilidad esencial** en el 98% de ofertas laborales para desarrolladores web. (Indeed 2025)
- compatible con **todos los frameworks** modernos (React, angolar, vue)

### Ejemplo mercado laboral
| Posición                | Requiere HTML  | Nivel de Exigencia |
|-------------------------|----------------|--------------------|
| Frontend Developer      | Sí (Avanzado)  | ★★★★★              |
| Full Stack Developer    | Sí (Intermedio)| ★★★★☆              |
| UX/UI Designer          | Sí (Básico)    | ★★☆☆☆              |
| Content Manager         | Sí (Básico)    | ★★☆☆☆              |
| SEO Specialist          | Sí (Intermedio)| ★★★☆☆              |

### Tendencias Actuales

1. **HTML5 como estándar dominante** (92% de Penetracion Global)
2. **Web Components** (Custom Elements + shadow DOM)
3. **Integración con tecnologías emergentes**:
    - Realidad Aumentada (`<model-viewer>`)
    - Aplicaciones PWA (Manifiestos web)
    - Email HTML para Merketing digital

---

## ¿Qué es HTML en profundidad?

* **Lenguaje de marcado** ➜ declara la **semántica** de cada parte (qué es), no cómo se verá.
* **Declarativo** ➜ describe el resultado deseado; el navegador decide la representación.
* **Independiente de plataforma** ➜ cualquier SO con *user agent* lo interpreta.

 **No posee lógica de control** (bucles, condicionales). Para interacción se recurre a JavaScript.

**Crear una pagina web es como construir un edificio:**

- 🧱 **HTML son los ladrillos**: Define la basica (donde val las paredes, puertas, ventanas)
- 🎨 **CSS es la pintura y decoración**: Decide los colores, estilos y especto visual
- 💡 **JavaScript es la electricidad**: Agrega interactividad y funciones dinamicas

### Analogias Cotidianas

1. **Como un periodico**:
    - HTML organiza las secciones (titulares, articulos, imagenes)
    - no define el tamaño de letras o colores (eso es CSS)

2. **Como el esqueleto humano**
    - HTML es la estructura osea (huesos)
    - CSS seria la piel y apariencia
    - JavaScript serian los musculos que permiten movimiento

---

## El ciclo de vida del documento y el DOM

### ¿Que es DOM

Imagina que el **DOM (Document Object Model)** es como un arbol genealogico de tu pagina web:

- 🌳 **Es una representación en memoria** de todos los elementos de tu página
- 🧩 **Organiza todo jerárquicamente**, como un árbol familiar con padres, hijos y hermanos
- 🔄 **Es dinámico y manipulable** con JavaScript, como si pudieras reorganizar las ramas del árbol

#### Analogía: El DOM como una cosa de muñecas

piensa en una casa de juguete donde:
- la cosa completa es el documento (`document`)
- cada habiracion es una seccion (`<div>`, `<section>`)
- los muevles son elementos individuales (`<p>`, `<img>`, `<button>`)
- puedes mover, añadir o quitar muebles (manipular el DOM con JavaScript)

#### Visuali del DOM

```
document
  └── html
      ├── head
      │   ├── title
      │   └── meta
      └── body
          ├── header
          │   └── h1
          ├── main
          │   ├── p
          │   └── img
          └── footer

```
### Como funciona realmente

1. **persin** el navegador lee tu codigo HTML y lo convierte en el arbol DOM
    - *Como leer los planos de una casa y construir una maqueta*

2. **Render tree:** combina el DOM (estructura) + CSSOM (estilos)
    - *como decidir que muebles van en cada habitacion y de que color*

3. **Layout:** calcula exactamente donde va cada elemento y que tamaño tiene
    - *Como medir cada habitacion y colocar los muebles en su sitio eacto*

4. **paint & composite:** dibuja todo en pantalla, capa por capa
    - *como pintar las paredes, colocar los muebles y hacer fotos del resultado*

### Por que es importante entender el DOM

- **para desarrolladores**: permite manupular la pagina dinamicamente
- **para optimizacion**: modificar el DOM cinstantemente es costoso (como estar moviendo muebles todo el tiempo)
- **para debugging**: cuando algo no se ve bien, necesitas entender que parte del arbol esta mal

> **consejo practico**: puedes ver el DOM de cualquier pagina web usando las herramientas de desarrollo del navegador (f12 o clic derecho -> "Inspeccionar")

## Estructura minima de un documento
```html
<!DOCTYPE html>
<html lang="es">
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1" />
    <title>Título de la página</title>
  </head>
  <body>
    <!-- Contenido visible -->
  </body>
</html>
```
### conceptos clave

| Término Técnico | Explicación para No-Técnicos | Ejemplo Real |
|-----------------|-----------------------------|--------------|
| Etiqueta (`<tag>`) | Instrucciones entre <> que dicen "esto es un título" o "aquí va una imagen" | Como poner "TÍTULO:" antes de un título en un documento |
| Atributo | Información extra para las etiquetas | Como decir "foto familiar, tamaño grande" |
| Elemento | La etiqueta + su contenido + atributos | Todo el paquete completo |

| Sección            | Propósito clave                                                                                        |
| ------------------ | ------------------------------------------------------------------------------------------------------ |
| `<!DOCTYPE html>`  | Activa **standards mode** y evita el modo *quirks* heredado de IE 5.                                   |
| `<html lang="es">` | Define el idioma principal (mejora accesibilidad, SEO y traducción automática).                        |
| `<head>`           | Solo **metadatos**: SEO, recursos externos, `meta`, `link`, `script defer`. *Nunca* contenido visible. |
| `<body>`           | Estructura semántica de la página: encabezados, artículos, navegación, etc.                            |

### 4.1 Metadatos esenciales

```html
<meta http-equiv="X-UA-Compatible" content="IE=edge" /> <!-- Evita modos de compatibilidad antiguos -->
<link rel="preconnect" href="https://fonts.gstatic.com" /> <!-- Optimiza conexiones -->
<link rel="stylesheet" href="/css/styles.css" />
<script defer src="/js/app.js"></script>
```

---
## Categorías de contenido en HTML5

| Categoría           | Ejemplos                                                   | Uso predictivo                                  |
| ------------------- | ---------------------------------------------------------- | ----------------------------------------------- |
| **Metadata**        | `base`, `link`, `meta`, `style`, `title`                   | Describen la página, no se renderizan.          |
| **Flow**            | Casi todos los elementos que se pueden anidar en `<body>`. |                                                 |
| **Sectioning**      | `header`, `footer`, `section`, `article`, `nav`, `aside`   | Definen la estructura jerárquica del documento. |
| **Heading**         | `h1–h6`                                                    | Representan títulos y subtítulos.               |
| **Phrasing**        | `span`, `a`, `em`, `strong`, `img`                         | Contenido en línea dentro de Flow.              |
| **Embedded**        | `img`, `video`, `canvas`, `iframe`                         | Contenido externo o interactivo.                |
| **Interactive**     | `a`, `button`, `details`, `summary`, `input`               | Elementos que aceptan interacción del usuario.  |
| **Form‑associated** | `form`, `input`, `label`, `select`, `textarea`             | Crean interfaces de entrada de datos.           |

Conocer estas categorías ayuda a evitar anidamientos inválidos y mejorar accesibilidad.

---

## Encabezados y jerarquía documental

* Solo \*\*un \*\***`<h1>`** por página favorece SEO, pero múltiples son válidos si representan distintas secciones.
* Los encabezados anidan **lógicamente** (no saltes de `<h1>` a `<h4>` sin necesidad).
* Motores de búsqueda y tecnologías asistivas usan esta jerarquía para crear índices.

```html
<h1>Guía de Jardinería</h1>
  <h2>Floración</h2>
    <h3>Bulbos</h3>
  <h2>Poda</h2>
```

---

## Texto, énfasis y significado

| Elemento | Semántica                  | Ejemplo                                               |
| -------- | -------------------------- | ----------------------------------------------------- |
| `strong` | Énfasis fuerte, relevancia | `¡<strong>Atención</strong>!`                         |
| `em`     | Énfasis sutil              | `Esto <em>quizá</em> funcione.`                       |
| `mark`   | Resaltado relevante        | `Resultado: <mark>42</mark>`                          |
| `small`  | Texto aclaratorio          | `© <small>2025</small>`                               |
| `abbr`   | Abreviaturas               | `<abbr title="HyperText Markup Language">HTML</abbr>` |

Usar la etiqueta correcta aporta significado y mejora lectores de pantalla.

---

## Listas avanzadas

* Las listas anidadas deben mantener coherencia en la indentación.
* `<dl>` listas de descripción: útil para glosarios o pares término‑definición.

```html
<dl>
  <dt>API</dt>
  <dd>Conjunto de reglas para comunicación software.</dd>
</dl>
```

---

## Enlaces profundizados

```html
<a href="/descarga.pdf" download>Descargar PDF</a>
<a href="https://example.com" target="_blank" rel="noopener noreferrer">Abrir en pestaña nueva</a>
```

* `rel="noopener noreferrer"` evita que la página nueva acceda a `window.opener` ⟶ mejora **seguridad**.
* Anclar dentro de la misma página: `<a href="#contacto">Ir a Contacto</a>`.
* Enlaces semánticos alternativos: `<link rel="canonical" href="https://dominio.com/original" />`.

---

## Imágenes y multimedia

### 10.1 Imágenes responsivas

```html
<picture>
  <source srcset="foto.avif" type="image/avif" />
  <source srcset="foto.webp" type="image/webp" />
  <img src="foto.jpg" alt="Atardecer en la playa" width="800" height="533" />
</picture>
```

* Usa formatos **AVIF/WebP** para compresión.
* `width` y `height` evitan *layout shift* (CLS) mejorando Core Web Vitals.
* Agrupa imagen + pie:

```html
<figure>
  <img src="grafico.svg" alt="Crecimiento trimestral" />
  <figcaption>Figura 1: Ventas 2024‑2025.</figcaption>
</figure>
```
### 10.2 Audio y video

```html
<video controls poster="preview.jpg">
  <source src="demo.mp4" type="video/mp4" />
  <track src="sub.es.vtt" kind="subtitles" srclang="es" label="Español" />
  Tu navegador no soporta video HTML5.
</video>
```

* Incluye subtítulos (`track`) para accesibilidad.
* Evita autoplay con sonido por experiencia de usuario.

---

## Tablas semánticas

```html
<table>
  <caption>Precios 2025</caption>
  <thead>
    <tr><th scope="col">Plan</th><th>Precio</th></tr>
  </thead>
  <tbody>
    <tr><th scope="row">Básico</th><td>$9</td></tr>
    <tr><th scope="row">Pro</th><td>$29</td></tr>
  </tbody>
</table>
```

* Usa `scope` para indicar cabeceras.
* Evita tablas para maquetar → usa CSS **Flexbox**/Grid.

---

## Formularios modernos

```html
<form action="/suscribirse" method="post" novalidate>
  <label for="email">Correo</label>
  <input type="email" id="email" name="email" required />

  <label>
    <input type="checkbox" name="terms" required /> Acepto términos
  </label>

  <button type="submit">Enviar</button>
</form>
```

* Atributos `required`, `pattern`, `min`, `max` permiten **validación nativa**.
* Usa `<fieldset>` + `<legend>` para agrupar controles.
* Atributos de accesibilidad: `aria-describedby`, `aria-invalid`.

---

## Etiquetas semánticas de HTML5

| Propósito                    | Elemento  | Uso típico                                        |
| ---------------------------- | --------- | ------------------------------------------------- |
| Cabecera global o de sección | `header`  | Logo, título, navegación principal                |
| Navegación                   | `nav`     | Conjunto de enlaces de navegación                 |
| Contenido principal          | `main`    | Una vez por documento. Excluye sidebars & footers |
| Artículo independiente       | `article` | Post de blog, comentario, tarjeta                 |
| Agrupación temática          | `section` | Capítulos, bloques, secciones de landing          |
| Complemento                  | `aside`   | Barra lateral, caja de tips                       |
| Pie de página                | `footer`  | Información legal, enlaces de soporte             |

---

## Atributos globales avanzados

* `data-*-`: guardar metadatos personalizados accesibles vía JS (`data-id`, `data-state`).
* `aria-*`: puente con **ARIA** para tecnologías asistivas (`aria-label`, `aria-live`).
* `role`: define la función del elemento (`role="alert"`, `role="button"`).
* `tabindex`: controla el orden de tabulación (usar con moderación).
* `contenteditable`: permite editar contenido en línea.

---

## Comentarios y entidades

```html
<!-- Comentario -->
&copy; &lt; &gt; &amp;  <!-- Entidades HTML -->
```

Usa entidades para caracteres reservados (<, >, &) o especiales (€,  ).

---

## Buenas prácticas ampliadas

1. **Semántica ante todo** ➜ facilita SEO y accesibilidad.
2. **Separación de responsabilidades** ➜ estructura (HTML), presentación (CSS), comportamiento (JS).
3. **Performance:** precargar (`preload`), comprimir imágenes, minificar.
4. **Accesibilidad (WCAG 2.1):** contraste suficiente, etiquetas de formulario, navegación con teclado.
5. **Seguridad:** sanitizar datos, evitar `javascript:` URLs, usar `Content‑Security‑Policy`.
6. **Progressive Enhancement:** página funcional sin JS; JS añade mejoras.

---

## SEO en HTML: Optimización para Motores de Búsqueda

El **SEO (Search Engine Optimization)** es el conjunto de técnicas para mejorar la visibilidad de un sitio web en los resultados orgánicos de los motores de búsqueda. HTML juega un papel fundamental, ya que proporciona la estructura semántica que los crawlers analizan.

### Fundamentos técnicos de SEO en HTML

1. **Estructura semántica**:
   - Usar jerarquía correcta de encabezados (`<h1>` a `<h6>`)
   - Emplear etiquetas como `<article>`, `<section>`, `<nav>`
   - Ejemplo:
     ```html
     <article itemscope itemtype="http://schema.org/Article">
       <h1 itemprop="headline">Título del artículo</h1>
       <meta itemprop="datePublished" content="2025-05-12">
     </article>
     ```

2. **Metadatos esenciales**:
   - `<title>`: 50-60 caracteres, incluye palabra clave principal
   - `<meta name="description">`: 150-160 caracteres, resumen atractivo
   - `<meta name="keywords">`: menos relevante hoy, pero aún considerado
   - Schema.org: vocabulario estructurado para rich snippets

3. **Atributos clave**:
   - `alt` en imágenes: describe contenido para crawlers y accesibilidad
   - `rel="nofollow"`: para enlaces que no deben pasar "link juice"
   - `canonical`: evita contenido duplicado

### SEO On-Page avanzado

| Elemento               | Buenas Prácticas                                                                 |
|------------------------|----------------------------------------------------------------------------------|
| URLs                   | Legibles, con keywords, sin parámetros innecesarios                              |
| Encabezados            | Jerarquía lógica, keywords estratégicas (no stuffing)                           |
| Contenido              | 1500+ palabras de calidad, estructura clara, keywords naturales                 |
| Velocidad de carga     | HTML optimizado, sin código redundante                                           |
| Mobile-first           | Diseño responsive (viewport meta tag esencial)                                   |
| Enlaces internos       | Anchor text descriptivo, estructura en "siloviki" (páginas importantes enlazadas) |

### Microdatos y Rich Snippets

```html
<div itemscope itemtype="http://schema.org/LocalBusiness">
  <h1 itemprop="name">Mi Negocio</h1>
  <p itemprop="address" itemscope itemtype="http://schema.org/PostalAddress">
    <span itemprop="streetAddress">Calle 123</span>
  </p>
  <span itemprop="telephone">555-1234</span>
</div>
```

Beneficios:
- Mejor CTR en resultados de búsqueda
- Información estructurada para asistentes de voz
- Compatibilidad con Knowledge Graph de Google

### Errores comunes

1. **Contenido oculto** (display:none sin justificación)
2. **Keyword stuffing** (repetición artificial de palabras clave)
3. **Títulos duplicados** o poco descriptivos
4. **Falta de atributos alt** en imágenes importantes
5. **Estructura de URLs pobre** (session IDs, parámetros largos)

### Herramientas SEO

* [Google Search Console](https://search.google.com/search-console)
* [Rich Results Test](https://search.google.com/test/rich-results)
* [Schema Markup Generator](https://technicalseo.com/tools/schema-markup-generator/)
* [Screaming Frog SEO Spider](https://www.screamingfrog.com/seo-spider/)

---