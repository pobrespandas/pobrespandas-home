# AGENTS.md — pobrespandas-home

## Propósito

Este repositorio contiene la home pública de pobrespandas. Firebase Hosting publica `public/` en:

- https://pobrespandas-principal.web.app

## Google Cloud y Firebase

- Proyecto de Google Cloud / Firebase: `gen-lang-client-0607406471`.
- Sitio Firebase Hosting: `pobrespandas-principal`.
- Target local de Firebase: `home` (definido en `.firebaserc`).

## Autenticación y verificación

No guardar tokens, claves ni archivos de credenciales en el repositorio.

Antes de operar, comprobar el contexto:

```sh
gcloud auth list
gcloud projects describe gen-lang-client-0607406471
firebase projects:list
firebase hosting:sites:list --project gen-lang-client-0607406471
```

La cuenta de Google debe tener permisos sobre `gen-lang-client-0607406471`. Si Firebase CLI no está autenticado, ejecutar `firebase login` de forma interactiva.

## Despliegue

1. Modificar sólo archivos dentro de `public/`.
2. Revisar los cambios y, si corresponde, commitearlos.
3. Validar sin publicar:

   ```sh
   firebase deploy --only hosting:home --project gen-lang-client-0607406471 --dry-run
   ```

4. Publicar:

   ```sh
   firebase deploy --only hosting:home --project gen-lang-client-0607406471
   ```

`firebase.json` define que sólo se publica `public/`. La caché local `.firebase/` está ignorada por Git.

## Editorial (hecho)

- Columnas `ideas` / `design` / `code` con ítems reales bilingües (AT-197).
- Extensiones Prime Agent como publicación del blog (`#extensions-post`, edición digital 002) y enlazadas desde la columna **code** (AT-198).
