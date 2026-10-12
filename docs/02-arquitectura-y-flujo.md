# Arquitectura y flujo

```text
src/main.ts
   |
   v
AppModule
   +-- BrowserModule
   +-- AppRoutingModule (sin rutas)
   +-- NgbModule
   |
   v
AppComponent -> plantilla + CSS + assets locales
```

La aplicación es monocomponente. `AppComponent` solo expone `title`; no hay servicios, modelos, pipes, guards, interceptores, estado compartido ni llamadas HTTP.

`AppRoutingModule` registra `RouterModule.forRoot([])`, pero la plantilla usa enlaces HTML y no contiene `router-outlet`. Bootstrap CSS se carga desde `angular.json`; `NgbModule` está importado, aunque el componente no usa directivas ng-bootstrap.

El flujo del usuario consiste en ver el banner y activar enlaces de fragmento. Como los destinos no existen, no se produce navegación útil dentro de la página.

No hay manejo de errores de negocio porque tampoco existen operaciones asíncronas o datos remotos.
