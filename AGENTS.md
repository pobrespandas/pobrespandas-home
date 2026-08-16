# AGENTS.md — pobrespandas-home

## Propósito

Este repositorio contiene la home pública de pobrespandas. Firebase Hosting publica `public/` en:

- https://pobrespandas.web.app

## Google Cloud y Firebase

- Proyecto de Google Cloud / Firebase: `pobrespandas-home`.
- Sitio Firebase Hosting: `pobrespandas`.
- Target local de Firebase: `home` (definido en `.firebaserc`).
- No usar el proyecto `gen-lang-client-0607406471` para esta home: es el proyecto anterior de pobrespandas y contiene otros recursos.

## Autenticación y verificación

No guardar tokens, claves ni archivos de credenciales en el repositorio.

Antes de operar, comprobar el contexto:

```sh
gcloud auth list
gcloud projects describe pobrespandas-home
firebase projects:list
firebase hosting:sites:list --project pobrespandas-home
```

La cuenta de Google debe tener permisos sobre el proyecto `pobrespandas-home`. Si Firebase CLI no está autenticado, ejecutar `firebase login` de forma interactiva.

## Despliegue

1. Modificar sólo archivos dentro de `public/`.
2. Revisar los cambios y, si corresponde, commitearlos.
3. Validar sin publicar:

   ```sh
   firebase deploy --only hosting:home --project pobrespandas-home --dry-run
   ```

4. Publicar:

   ```sh
   firebase deploy --only hosting:home --project pobrespandas-home
   ```

`firebase.json` define que sólo se publica `public/`. La caché local `.firebase/` está ignorada por Git.

## Editorial (hecho)

- Columnas `ideas` / `design` / `code` con ítems reales bilingües (AT-197).
- Extensiones Prime Agent como publicación del blog (`#extensions-post`, edición digital 002) y enlazadas desde la columna **code** (AT-198).
