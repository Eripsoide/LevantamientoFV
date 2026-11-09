# Levantamiento FV — PWA

## Contenido
index.html · manifest.webmanifest · sw.js · vendor/ (pdf.js local) · icons/

## 1. Publicar (necesita HTTPS)
- **Netlify:** app.netlify.com/drop → arrastra esta carpeta completa.
- **GitHub Pages:** sube la carpeta a un repo → Settings → Pages.
- **Cloudflare Pages:** "Upload assets" con la carpeta.
No abras index.html con doble clic: el service worker solo funciona con https:// (o localhost).

## 2. Instalar
- **iPad:** abre el enlace en Safari → Compartir → "Añadir a pantalla de inicio" → ábrela desde el ícono.
- **Android:** Chrome → botón "Instalar app" de la portada (o menú ⋮ → Instalar).
Abre la app una vez con internet para que se guarde todo; después funciona sin conexión.

## 3. Protección de datos
- Los proyectos viven en IndexedDB (fotos incluidas), y la app pide almacenamiento persistente al abrir.
- En iPad, instalada en pantalla de inicio, no aplica el borrado de 7 días de Safari.
- La portada muestra el estado (✓ protegido / sin protección) y la fecha del último respaldo.
- "Respaldar" abre la hoja Compartir en iPad (Guardar en Archivos, AirDrop, iCloud Drive) o descarga el .json.
- "Importar" ahora COMBINA con lo que ya tienes (gana el más reciente); ya no reemplaza todo.

## 4. Actualizar la app
Edita index.html, cambia VERSION en sw.js (p. ej. 'fv-v2') y vuelve a publicar.
La app mostrará "Hay una nueva versión · Actualizar". Los datos no se tocan.

## Importante
Los datos son por dispositivo y por dirección (URL). Si cambias de dominio, la app arranca vacía: restaura con un respaldo.
