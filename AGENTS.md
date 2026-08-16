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

## Pendientes

- Inventar contenido real para las columnas `ideas`, `design` y `code` de `public/index.html`. Hoy son placeholders del eslogan (all my life / chewing bamboo / digital edition / etc.) y apuntan a `#publication`. Mantener el layout de 3 columnas y el bilingüismo EN|ES.
