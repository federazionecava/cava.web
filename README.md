# comitatocava.org

Web de presentación del CAVA (Comitato delle Associazioni Venete dell'Argentina) para la **Consulta dei Veneti nel Mondo 2026**. No es la landing institucional completa: presenta qué es el CAVA en el marco de la Consulta. Las menciones al evento están en el `<head>` (title, description, og/twitter), en la etiqueta `.event-badge` del hero y en el footer. Sitio estático en HTML, CSS y JS puros: no hace falta instalar ni compilar nada.

## Estructura

```
index.html          la página: hero, chi siamo, la rete (mapa), il ruolo delle associazioni, contatti
css/style.css       todo el diseño. Colores y medidas, arriba de todo en :root
js/main.js          animaciones, nav, menú, mapa, chips de sedes (celular), contadores, video de fondo
assets/fonts/       ZT Nature (la tipografía del CAVA)
assets/img/         logo, íconos y og.jpg (vista previa al compartir)
video/              video de fondo (720p, sin audio)
favicon.ico         ícono de la pestaña
site.webmanifest    íconos para "agregar a inicio" en celulares
```

## Verlo

Abrí `index.html` con doble clic. Para verlo como en un servidor real, desde esta carpeta:

```bash
npx serve .        # o: python -m http.server
```

## Publicar (Vercel)

Proyecto de Vercel conectado a este repo, con *Framework Preset* en **Other** y *Build Command* y *Output Directory* vacíos. En **Settings → Domains** van `comitatocava.org` y `www.comitatocava.org` (que redirige al primero). El DNS está en Vercel, así que no hay que tocar registros.

## Editar

- Los textos están directamente en `index.html`.
- Para cambiar el video, reemplazá `video/landing.mp4` (mp4 H.264, sin audio, idealmente < 5 MB). La sección *Il ruolo* busca `video/associazioni.mp4`. Si no existe, muestra el gradiente.
- La vista previa al compartir (WhatsApp, etc.) usa `og:title`, `og:description` y `og:image`, en el `<head>`. Si cambiás `og.jpg`, subí el `?v=` de su dirección, porque WhatsApp guarda en caché las vistas previas.
- Si cambia el dominio, buscá y reemplazá `https://comitatocava.org` en `index.html`.
