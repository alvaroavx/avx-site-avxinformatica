# Guía para agentes

Este repositorio es un prototipo Angular histórico e independiente. No asumas que es el sitio AVX publicado ni que los destinos del menú existen.

## Antes de modificar

1. Lee `README.md` y `docs/README.md`.
2. Revisa `git status --short --branch` y conserva cambios previos, especialmente `yarn.lock` mientras siga modificado.
3. Traza el cambio desde `AppModule` y `AppComponent`; no hay servicios, modelos ni rutas funcionales.
4. Separa implementación, intención visible, limitación y recomendación.

## Reglas

- No documentes los enlaces del menú como secciones implementadas.
- No inventes API, backend, CMS, despliegue o ambiente activo.
- Usa rutas de assets compatibles con el `base href` y el pipeline Angular.
- Añade texto alternativo y semántica al tocar la interfaz.
- Evita anidar enlaces dentro de botones en cambios futuros.
- Ajusta la prueba heredada si cambia `AppComponent`.
- Elige un gestor de paquetes antes de regenerar locks; existen `package-lock.json` y `yarn.lock`.
- No agregues `dist/` ni `node_modules/`.

## Validación mínima

```bash
npm run build
npm test -- --watch=false --browsers=ChromeHeadless
git diff --check
```

El contenedor y Kubernetes requieren validación separada. Commit o push solo con solicitud explícita.
