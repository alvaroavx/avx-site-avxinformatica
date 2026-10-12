# Desarrollo y configuración

## Herramientas declaradas

- Angular 13.2.x; CLI/build 13.1.x.
- TypeScript 4.4.x, RxJS 7.4 y Zone.js 0.11.
- Bootstrap 4.6 y ng-bootstrap 11.
- Node exacto no declarado para desarrollo; Docker usa Node 17.6.0.

```bash
npm ci
npm start
npm run build
npm test -- --watch=false --browsers=ChromeHeadless
```

`npm start` usa el ambiente development. `npm run build` usa production por defecto y genera `dist/avx-site/`. Producción activa hashing y presupuestos: 500 kB/1 MB para el bundle inicial y 2/4 kB por estilo de componente.

Existen `package-lock.json` y `yarn.lock`. Hasta decidir gestor canónico, evita regenerar ambos. El Dockerfile copia `package*.json` y ejecuta `npm install`, así que operacionalmente sigue la ruta npm.

No hay configuración comercial por ambiente. Texto, navegación y contenido viven en `app.component.html`.
