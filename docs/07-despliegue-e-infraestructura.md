# Despliegue e infraestructura

## Docker

El Dockerfile construye en `node:17.6.0`, instala con `npm install`, compila según el argumento `configuration` —development por defecto— hacia `dist/out/` y copia ese resultado a `nginx:1.15`.

Riesgos: imágenes antiguas, dependencias no instaladas con `npm ci`, build de desarrollo por defecto y ausencia de pin por digest o healthcheck.

## Nginx

Sirve `/usr/share/nginx/html`, aplica fallback a `index.html`, gzip y expiración por tipo. HTML expira de inmediato; CSS, JavaScript, JSON e imágenes usan expiración máxima. No hay TLS porque normalmente se resolvería fuera del contenedor, pero esa capa no está descrita.

## Kubernetes

`deployment.yaml` declara una réplica de `avx/avx-site:v1` en puerto 80. El manifiesto carece de `spec.selector`, Service, Ingress, probes, recursos, estrategia, namespace y políticas. En `apps/v1`, la ausencia de selector impide considerar el Deployment listo para aplicar.

## Evidencia operacional

No hay CI/CD, registry configurado, dominio, cluster, ambientes, monitoreo, logs centralizados, rollback o respaldo. Los archivos representan intención de empaquetado, no un despliegue probado.
