# AVX Informática — prototipo Angular

Segundo intento histórico del sitio corporativo de AVX Informática, desarrollado con Angular 13. El repositorio implementa el banner inicial: navegación, logotipo, propuesta de valor y un llamado a conocer servicios.

El menú anticipa servicios, portafolio, partners, testimonios y contacto, pero esas secciones no están implementadas. Este repositorio tampoco acredita una publicación vigente; el sitio AVX activo vive en otro proyecto.

## Estado funcional

| Área | Estado comprobado |
| --- | --- |
| Banner de portada | Implementado en `AppComponent` |
| Logo, fondo y Metropolis | Incluidos en `src/assets/` |
| Menú y CTA | Renderizados, pero apuntan a IDs ausentes |
| Rutas Angular | Módulo existente con arreglo vacío |
| Componentes adicionales | No existen |
| API, datos, formularios, CMS | No existen |
| Contenedor | Docker multi-stage Node/Nginx |
| Kubernetes | Deployment incompleto; no incluye selector ni Service |
| Pruebas | Dos expectativas válidas y una heredada obsoleta |

## Uso local

```bash
npm ci
npm start
npm test -- --watch=false --browsers=ChromeHeadless
npm run build
```

El servidor usa normalmente `http://localhost:4200`. El build produce `dist/avx-site/`; el Dockerfile fuerza `dist/out/` dentro de la imagen.

## Mapa rápido

- `src/app/app.component.*`: toda la interfaz visible.
- `src/app/app-routing.module.ts`: router sin rutas.
- `src/styles.css`: fuentes y estilos globales.
- `src/assets/`: fondo, logos y familia Metropolis.
- `angular.json`: build, test y presupuestos.
- `Dockerfile`, `nginx-custom.conf`: construcción y servicio estático.
- `deployment.yaml`: borrador de Deployment Kubernetes.
- [`docs/README.md`](docs/README.md): documentación técnica.
- [`AGENTS.md`](AGENTS.md): reglas para agentes.
- [`llms.txt`](llms.txt): contexto compacto para IA.

Documentación revisada desde código, configuración e historial Git el 12 de octubre de 2026. El cambio preexistente de `yarn.lock` no forma parte de esta revisión documental.
