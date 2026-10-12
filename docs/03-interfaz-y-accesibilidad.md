# Interfaz y accesibilidad

## Lenguaje visual

Fondo negro, imagen luminosa central, logo claro, tipografía Metropolis y resplandor azul construyen una estética tecnológica/espacial. Los recursos están versionados en `src/assets/`.

## Adaptación actual

Solo cambia el ancho máximo del logo en 480, 768 y 1024 px. El menú conserva `display: table`, celdas de 150 px y padding horizontal de 100 px; el texto introductorio mantiene 24 px y padding amplio. Esto implica riesgo de desborde o compresión en pantallas pequeñas.

## Accesibilidad observada

- El logo no tiene atributo `alt`.
- No hay `h1`, landmarks ni enlace de salto.
- El CTA anida un `<a>` dentro de `<button>`, combinación de controles interactivos inválida.
- Las animaciones de resplandor no respetan `prefers-reduced-motion`.
- El foco hereda casi el mismo tratamiento animado que hover; no hay evidencia de navegación completa por teclado.
- El documento declara `lang="en"` aunque el contenido está en español.

Antes de ampliar contenido, corregir semántica, idioma, foco, movimiento reducido y composición móvil.
