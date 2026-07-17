# Liga Gastronómica Onubense — de web a APK

Esta carpeta contiene una app web independiente (no depende de Claude):
- `index.html` — la app entera (funciona sola con doble clic)
- `manifest.json` — la ficha de identidad de la app (nombre, icono, colores)
- `service-worker.js` — permite que funcione offline
- `icon-192.png` / `icon-512.png` — el icono

Los datos se guardan con `localStorage`, es decir, **en el propio navegador/dispositivo**, no en tu cuenta de Claude. Si borras datos del navegador o cambias de móvil, no se sincronizan solos.

## Paso 1 — Súbela a un hosting gratuito

Necesitas una URL pública (PWA Builder no admite carpetas locales). La más sencilla:

**Opción GitHub Pages**
1. Crea una cuenta en github.com si no tienes.
2. Crea un repositorio nuevo (público), por ejemplo `liga-onubense`.
3. Sube estos 5 archivos (botón "Add file → Upload files").
4. Ve a Settings → Pages → en "Branch" elige `main` y guarda.
5. En un par de minutos tendrás una URL tipo `https://tuusuario.github.io/liga-onubense/`.

**Opción Netlify (aún más rápida, sin cuenta de GitHub)**
1. Entra en netlify.com → "Deploy manually" / "Drag and drop".
2. Arrastra la carpeta completa `liga-app`.
3. Te da una URL al momento, tipo `https://algo-random.netlify.app`.

## Paso 2 — Genera el APK con PWA Builder

1. Ve a **pwabuilder.com**.
2. Pega tu URL (la de GitHub Pages o Netlify) y pulsa "Start".
3. Te analizará la web y te dirá que es una PWA válida (gracias al manifest y al service worker que ya están incluidos).
4. Pulsa "Package for stores" → elige **Android**.
5. Descarga el paquete: te da un `.apk` (o `.aab` si prefieres subirlo a Google Play).

## Paso 3 — Instalar el APK en tu móvil

1. Pasa el `.apk` a tu Android (por cable, Drive, WhatsApp a ti mismo, etc.).
2. Ábrelo desde el móvil. Te pedirá permiso para "instalar apps de origen desconocido" la primera vez — actívalo solo para esa app.
3. Se instala como una app normal, con su icono en el cajón de apps.

## Notas
- Si más adelante quieres cambiar colores, categorías o textos, todo está en `index.html` (es un único archivo, fácil de tocar).
- Si prefieres no pelearte con hosting/PWA Builder, la opción más rápida sigue siendo "Añadir a pantalla de inicio" desde el navegador, que no requiere ningún paso de estos.
