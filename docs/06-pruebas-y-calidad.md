# Pruebas y calidad

`app.component.spec.ts` contiene tres casos:

1. creación del componente;
2. valor `avx-site` en `title`;
3. búsqueda de `.content span` con `avx-site app is running!`.

El tercer caso proviene del scaffold y no coincide con la plantilla; está obsoleto. Los dos primeros cubren arranque mínimo, no conducta de usuario.

No hay pruebas para enlaces, IDs de destino, assets, accesibilidad, responsive, Docker, Nginx o Kubernetes. Tampoco hay pruebas E2E configuradas.

```bash
npm run build
npm test -- --watch=false --browsers=ChromeHeadless
git diff --check
```

Karma requiere un Chrome/Chromium compatible. Una prueba local no demuestra la imagen de contenedor ni el despliegue. La corrección recomendada es probar el mensaje y navegación reales, no reintroducir el texto del scaffold.
