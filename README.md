# Data Analyst Portfolio — Visionary Insights

Portafolio web estático que presenta proyectos, habilidades y una vista previa interactiva con Chart.js. Está escrito en HTML/CSS/vanilla JS y diseñado para mostrar trabajos como analista de datos y arquitecto de datos.

## Vista rápida
- Archivo principal: `index.html`
- Diseño oscuro con tipografías Google Fonts, iconos Lucide y una gráfica creada con Chart.js.

## Tecnologías
- HTML5, CSS (variable fonts), JavaScript (vanilla)
- Chart.js (visualizaciones)
- Lucide Icons

## Cómo ejecutar localmente
Opciones rápidas:

1. Abrir `index.html` en el navegador (basta para contenido estático). 

2. Servidor estático simple (recomendado para que Chart.js y fetch funcionen correctamente):

   - Con Python 3:
     ```bash
     python -m http.server 8000
     # luego abrir http://localhost:8000
     ```

   - Con `serve` (Node):
     ```bash
     npm install -g serve
     serve .
     ```

## Estructura de archivos
- `index.html` — página principal

## Sugerencias y mejoras recomendadas
A continuación incluyo mejoras prioritarias (seguridad, rendimiento, accesibilidad y mantenibilidad). Puedo o puedo aplicarlas en PRs separados si quieres.

1. Rendimiento
   - Mover y/o añadir `defer` a los scripts externos (Chart.js y Lucide) para no bloquear el renderizado:
     ```html
     <script src="https://cdn.jsdelivr.net/npm/chart.js" defer></script>
     <script src="https://unpkg.com/lucide@latest" defer></script>
     ```
   - Prefetch / preconnect para Google Fonts:
     ```html
     <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
     ```
   - Extraer CSS en un archivo separado (`styles.css`) para mejor cache y mantenimiento.

2. Seguridad y estabilidad
   - Evitar usar `@latest` en CDNs para evitar rupturas; fijar una versión conocida de Lucide y Chart.js.
   - Añadir Subresource Integrity (SRI) y `crossorigin` cuando el CDN lo permita.

3. Accesibilidad
   - Añadir `meta name="description"` para SEO y accesibilidad:
     ```html
     <meta name="description" content="Portafolio de analista de datos: proyectos de ML, visualización y arquitectura de datos.">
     ```
   - Incluir un "skip link" al inicio para usuarios con teclado:
     ```html
     <a class="skip-link" href="#main">Saltar al contenido</a>
     ```
   - Añadir `aria-label` o `role` a elementos interactivos y `alt` donde aplique.
   - Mejorar el contraste en algunos elementos y añadir `:focus` styles visibles.

4. Mantenibilidad y buenas prácticas
   - Evitar estilos inline — mover estilos y pequeñas utilidades al CSS.
   - Separar datos de la visualización: mantener datos de Chart.js en un archivo JSON o en un bloque JS separado.
   - Remplazar `mailto:` por un formulario (o usar un servicio de envío) para evitar spam.

5. Progressive Enhancement
   - Añadir `<noscript>` con mensaje o contenido alternativo si JS está deshabilitado.

6. Pequeñas recomendaciones de código
   - Añadir `alt`/`aria-hidden` a iconos transformados por Lucide si los SVG resultantes no aportan información semántica.
   - Usar elementos semánticos correctamente (ya usas `main`, revisar orden de headings h1→h2→h3).

## ¿Quieres que aplique los cambios?
Puedo:
- 1) Crear un PR con los cambios (separados: rendimiento, accesibilidad, estructura), o
- 2) Hacer commits directos aquí (si prefieres). 

Si quieres que implemente algunos cambios ahora, dime cuáles priorizamos (por ejemplo: mover scripts + agregar meta description + extraer CSS) y lo hago.

---

_Archivo generado automáticamente por Copilot para el repositorio._
