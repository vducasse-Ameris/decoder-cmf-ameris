# Decoder de Cartera B.2 + B.5 — Ameris AGF

Dashboard interno de Ameris para análisis de carteras de inversión de las
compañías de seguros chilenas, basado en los archivos B.2 (cuotas FFII
nacionales) y B.5 (inversiones en el extranjero) que la CMF publica
mensualmente.

## Vista pública

`https://<usuario-github>.github.io/<nombre-repo>/`

(la URL se completa una vez que GitHub Pages esté habilitado en este repo)

## Cómo usarlo

1. Descargar archivos B.2 (`aAAAAMMv.RUT`) y/o B.5 (`xAAAAMMv.RUT`) desde
   [el sitio de la CMF](https://www.cmfchile.cl)
2. Abrir la URL del dashboard
3. Arrastrar los archivos a la zona azul (B.2) o morada (B.5)
4. Navegar las pestañas: Resumen General · Por AGF · Por Compañía ·
   Instrumentos · Evolución · Extranjero (B.5) · Pulso Ameris

## Pestañas

| Pestaña | Qué muestra |
|---|---|
| Resumen General | KPIs sistema, distribución por categoría, top AGFs y top compañías |
| Por AGF | Ranking de administradoras con drill-down a fondo + compañía cliente |
| Por Compañía de Seguros | Tarjetas expandibles por aseguradora, vista por categoría / por AGF |
| Instrumentos | Listado consolidado de fondos únicos |
| Evolución | Sparklines + gráfico mensual + top movers |
| Extranjero (B.5) | Bonos y fondos extranjeros, drill-down por compañía |
| Pulso Ameris | Vista 360° para Ameris AGF: AUM, ranking, market share, concentración |

## Privacidad

**Todo el procesamiento es client-side.** Los archivos cargados nunca salen
del navegador del usuario. La data se guarda en `localStorage` de cada
navegador. Esto hace seguro publicar el link aunque el dashboard procese
información regulatoria sensible.

## Estructura

```
index.html      — Dashboard completo (HTML + CSS + JS)
maps.js         — RUT_AGF_MAP, NEMO_NAME_MAP, INSURER_NAME_OVERRIDES,
                  FILENAME_RUT_TO_INSURER (mappings de identificación)
ameris-logo-*   — Logos corporativos Ameris
favicon-*       — Iconos del tab del navegador
```

## Stack técnico

- HTML / CSS / JavaScript vanilla (sin frameworks ni build step)
- Embedded SVG charts (sparklines, line charts, bar charts, donut)
- LocalStorage para persistencia client-side
- Sin backend — sirve como static site en cualquier CDN

## Deploy

GitHub Pages: Settings → Pages → Source: `main` branch / `/ (root)`.

Cualquier `git push` a `main` actualiza la URL pública en ~30 segundos.

## Mantenimiento

Las correcciones de nombres de fondos y AGFs se hacen editando `maps.js`
directamente. El código de parsing y rendering vive en `index.html` (en
el bloque `<script>` al final).

## Contacto

Ameris AGF · vducasse@ameris.cl · Av. El Golf 82, Piso 5, Las Condes
