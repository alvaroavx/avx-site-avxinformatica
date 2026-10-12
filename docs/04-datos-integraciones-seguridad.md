# Datos, integraciones y seguridad

No existe capa de datos. Los archivos `environment.ts` y `environment.prod.ts` solo contienen la bandera `production`; no definen URLs ni secretos.

No hay `HttpClientModule`, servicios HTTP, formularios, cookies, almacenamiento web, analítica o integraciones externas. Bootstrap y Angular se instalan como paquetes de build; las fuentes e imágenes se sirven localmente.

No hay autenticación, autorización, roles ni información personal. La seguridad de dominio, HTTPS, cabeceras y plataforma no puede derivarse del frontend.

Nginx configura caché por tipo, gzip y fallback a `index.html`. No define CSP u otras cabeceras de seguridad. La versión real de una imagen desplegada y la configuración del cluster no están verificadas.

Un Dockerfile o manifiesto no demuestra que una imagen se haya construido, publicado o ejecutado.
