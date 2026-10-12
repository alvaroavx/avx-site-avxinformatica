# Guía de mantenimiento

| Necesidad | Archivo | Validación |
| --- | --- | --- |
| Contenido y menú | `app.component.html` | prueba + inspección de destinos |
| Presentación | `app.component.css` | build + móvil + teclado |
| Fuentes/globales | `src/styles.css` | build + revisión visual |
| Assets | `src/assets/` | build + revisar red del navegador |
| Rutas | `app-routing.module.ts` y plantilla | pruebas de navegación |
| Build | `angular.json`, environments | build por ambiente |
| Contenedor | `Dockerfile`, Nginx | construir y ejecutar imagen |
| Kubernetes | `deployment.yaml` | validación de esquema + cluster autorizado |

Flujo seguro: revisar Git, preservar `yarn.lock`, modificar al dueño del comportamiento, ajustar pruebas, ejecutar build/test/`git diff --check` y actualizar docs.

Si faltan estilos o imágenes, revisa mayúsculas y rutas bajo `assets/`. Si el menú no desplaza, confirma que exista el ID de destino. Si el test busca `app is running`, es el caso heredado conocido. Si Docker difiere del build local, recuerda que fuerza `dist/out` y que su configuración predeterminada es development.
