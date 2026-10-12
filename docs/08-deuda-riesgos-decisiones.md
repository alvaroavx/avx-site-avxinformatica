# Deuda, riesgos y decisiones

| Tema | Evidencia | Consecuencia |
| --- | --- | --- |
| Navegación vacía | Cinco fragmentos sin IDs | Promesa de contenido sin destino |
| Prueba obsoleta | Busca `.content span` | Suite roja o señal falsa |
| Responsive parcial | Menú tabular y padding fijo | Riesgo móvil alto |
| Semántica | Sin alt/h1; botón con enlace | Accesibilidad deficiente |
| Dependencias e imágenes antiguas | Angular 13, Node 17.6, Nginx 1.15 | Mantenimiento y seguridad requieren evaluación |
| Kubernetes incompleto | Sin selector ni Service | No es desplegable como solución completa |
| Dos lockfiles | npm y Yarn | Resoluciones divergentes |

El riesgo principal es completar este prototipo sin resolver su relación con el sitio activo, duplicando producto e identidad.

Decisiones pendientes: archivar, migrar ideas o reactivar; elegir repositorio canónico; escoger npm o Yarn; decidir si conservar Angular; definir si Docker/Kubernetes siguen siendo necesarios.

Si se retoma: primero decidir rol, luego corregir pruebas/semántica/responsive, después completar contenido y finalmente modernizar infraestructura con validación real.
