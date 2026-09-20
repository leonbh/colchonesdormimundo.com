# Contexto del proyecto

Landing page estática de una sola página (`index.html`) con animación por frames
en canvas. Desplegada en Vercel.

## Infraestructura

- **Hosting:** Vercel — team `leonbhs-projects`, proyecto `colchonesdormimundo-com`
  (`prj_Lalw9qGOIK9ppPU9QkYiwuQBPV5G`)
- **DNS:** gestionado por Vercel (`ns1`/`ns2.vercel-dns.com`)
- **Repo:** `github.com/leonbh/colchonesdormimundo.com`

## Estado actual — 19/09/2026

El sitio está **fuera de uso**. Todo el tráfico de `colchonesdormimundo.com` y
`www.colchonesdormimundo.com` redirige a `dormimundo.com.mx` mediante el bloque
`redirects` de `vercel.json`.

Decisiones tomadas:

- **Redirect en lugar de proyecto pausado.** Pausar el proyecto devolvía 503, lo
  que deja al visitante sin salida. El redirect lo manda al sitio corporativo.
- **`permanent: false` (307), no 308.** La pausa es temporal; un 308 se cachea de
  forma agresiva en los navegadores y complicaría revertir cuando la página
  vuelva a usarse.
- **Sin `/$1` en el destino.** Es una landing de una sola página: reenviar la
  ruta generaría 404 en el dominio destino.

El código de la landing sigue intacto en el repo — solo se antepone el redirect.

## Para reactivar la página

Quitar el bloque `redirects` de `vercel.json` y desplegar con
`vercel deploy --prod`.

## Siguiente paso recomendado

Revisar en `vercel.com/domains` cuándo vence `colchonesdormimundo.com` y decidir
si conviene seguir renovándolo mientras el sitio no se use.
